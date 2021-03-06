---
title: ISNULL (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 31e0b77e397bd4f190119a01719da185211f7715
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isnull-entity-sql"></a>ISNULL (Entity SQL)
确定查询表达式是否为 null。  
  
## <a name="syntax"></a>语法  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a>参数  
 `expression`  
 任何有效的查询表达式。 不可以是集合，不可含有集合成员，也不可以是具有集合类型属性的记录类型。  
  
 NOT  
 对 IS NULL 的 EDM.Boolean 结果取反。  
  
## <a name="return-value"></a>返回值  
 如果 `true` 返回 null，则为 `expression`；否则为 `false`。  
  
## <a name="remarks"></a>备注  
 使用 `IS NULL` 可确定外部联接的元素是否为 null：  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 使用 `IS NULL` 可确定成员是否有实际值：  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 下表显示了 `IS NULL` 对于某些模式的行为。 所有异常都在调用提供程序之前从客户端引发：  
  
|模式|行为|  
|-------------|--------------|  
|null IS NULL|返回 `true`。|  
|TREAT (null AS EntityType) IS NULL|返回 `true`。|  
|TREAT (null AS ComplexType) IS NULL|引发错误。|  
|TREAT (null AS RowType) IS NULL|引发错误。|  
|EntityType IS NULL|返回 `true` 或 `false`。|  
|ComplexType IS NULL|引发错误。|  
|RowType IS NULL|引发错误。|  
  
## <a name="example"></a>示例  
 下面的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询使用 IS NOT NULL 运算符来确定查询表达式是否不为 null。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  执行 [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2.  将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a>另请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
