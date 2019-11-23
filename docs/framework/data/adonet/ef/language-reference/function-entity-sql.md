---
title: FUNCTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: bacc773351812a5db60f493f3025c8e4b07dbaa2
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833800"
---
# <a name="function-entity-sql"></a><span data-ttu-id="d1b24-102">FUNCTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d1b24-102">FUNCTION (Entity SQL)</span></span>
<span data-ttu-id="d1b24-103">Definiert eine Funktion im Bereich eines Entity SQL-Abfragebefehls.</span><span class="sxs-lookup"><span data-stu-id="d1b24-103">Defines a function in the scope of an Entity SQL query command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1b24-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1b24-104">Syntax</span></span>  
  
```sql  
FUNCTION function-name  
( [ { parameter_name <type_definition>   
        [ ,...n ]  
  ]  
) AS ( function_expression )   
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition> )   
                | REF ( data_type )   
                | ROW ( row_expression )   
        }   
```  
  
## <a name="arguments"></a><span data-ttu-id="d1b24-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d1b24-105">Arguments</span></span>  
 `function-name`  
 <span data-ttu-id="d1b24-106">Name der Funktion.</span><span class="sxs-lookup"><span data-stu-id="d1b24-106">Name of the function.</span></span>  
  
 `parameter-name`  
 <span data-ttu-id="d1b24-107">Der Name eines Parameters in der Funktion.</span><span class="sxs-lookup"><span data-stu-id="d1b24-107">Name of a parameter in the function.</span></span>  
  
 `function_expression`  
 <span data-ttu-id="d1b24-108">Ein gültiger Entity SQL-Ausdruck, der die Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="d1b24-108">A valid Entity SQL expression that is the function.</span></span> <span data-ttu-id="d1b24-109">Der Befehl in der Funktion kann auf `parameter_name` -Parameter, die an die Funktion übergeben wurden, angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d1b24-109">The command in the function can act on `parameter_name` parameters passed to the function.</span></span>  
  
 `data_type`  
 <span data-ttu-id="d1b24-110">Der Name eines unterstützten Typs.</span><span class="sxs-lookup"><span data-stu-id="d1b24-110">Name of a supported type.</span></span>  
  
 <span data-ttu-id="d1b24-111">COLLECTION ( <type_definition`>` )</span><span class="sxs-lookup"><span data-stu-id="d1b24-111">COLLECTION ( <type_definition`>` )</span></span>  
 <span data-ttu-id="d1b24-112">Ein Ausdruck, der eine Auflistung von unterstützten Typen, Zeilen oder Verweisen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d1b24-112">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
 <span data-ttu-id="d1b24-113">REF **(** `data_type` **)**</span><span class="sxs-lookup"><span data-stu-id="d1b24-113">REF **(**`data_type`**)**</span></span>  
 <span data-ttu-id="d1b24-114">Ein Ausdruck, der einen Verweis auf einen Entitätstyp zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d1b24-114">An expression that returns a reference to an entity type.</span></span>  
  
 <span data-ttu-id="d1b24-115">ROW **(** `row_expression` **)**</span><span class="sxs-lookup"><span data-stu-id="d1b24-115">ROW **(**`row_expression`**)**</span></span>  
 <span data-ttu-id="d1b24-116">Ein Ausdruck, der anonyme strukturell eingegebene Datensätze von mindestens einem Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d1b24-116">An expression that returns anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="d1b24-117">Weitere Informationen finden Sie unter [ROW](row-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d1b24-117">For more information, see [ROW](row-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1b24-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d1b24-118">Remarks</span></span>  
 <span data-ttu-id="d1b24-119">Mehrere Funktionen mit dem gleichen Namen können inline deklariert werden, sofern sie unterschiedliche Funktionssignaturen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d1b24-119">Multiple functions with the same name can be declared inline, as long as the function signatures are different.</span></span> <span data-ttu-id="d1b24-120">Weitere Informationen finden Sie unter [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d1b24-120">For more information, see [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span></span>  
  
 <span data-ttu-id="d1b24-121">Eine Inlinefunktion kann nur in einem Entity SQL-Befehl aufgerufen werden, nachdem sie in diesem Befehl definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d1b24-121">An inline function can be called in an Entity SQL command only after it has been defined in that command.</span></span> <span data-ttu-id="d1b24-122">Eine Inlinefunktion kann jedoch in einer anderen Inlinefunktion aufgerufen werden, bevor oder nachdem die aufgerufene Funktion definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d1b24-122">However, an inline function can be called inside another inline function either before or after the called function has been defined.</span></span> <span data-ttu-id="d1b24-123">Im folgenden Beispiel wird Funktion B von Funktion A aufgerufen, bevor Funktion B definiert wird:</span><span class="sxs-lookup"><span data-stu-id="d1b24-123">In the following example, function A calls function B before function B is defined:</span></span>  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 <span data-ttu-id="d1b24-124">Weitere Informationen finden Sie unter [Gewusst wie: Aufrufen einer benutzerdefinierten Funktion](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d1b24-124">For more information, see [How to: Call a User-Defined Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)).</span></span>  
  
 <span data-ttu-id="d1b24-125">Funktionen können auch im Modell selbst deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="d1b24-125">Functions can also be declared in the model itself.</span></span> <span data-ttu-id="d1b24-126">Im Modell deklarierte Funktionen werden auf die gleiche Weise ausgeführt wie Funktionen, die inline im Befehl deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="d1b24-126">Functions declared in the model are executed in the same way as functions declared inline in the command.</span></span> <span data-ttu-id="d1b24-127">Weitere Informationen finden Sie unter [benutzerdefinierte Funktionen](user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d1b24-127">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1b24-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d1b24-128">Example</span></span>  
 <span data-ttu-id="d1b24-129">Der folgende Entity SQL-Befehl definiert eine `Products` -Funktion, die die zurückgegebenen Produkte anhand eines ganzzahligen Werts filtert.</span><span class="sxs-lookup"><span data-stu-id="d1b24-129">The following Entity SQL command defines a function `Products` that takes an integer value to filter the returned products.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION1](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function1)]  
  
## <a name="example"></a><span data-ttu-id="d1b24-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d1b24-130">Example</span></span>  
 <span data-ttu-id="d1b24-131">Der folgende Entity SQL-Befehl definiert eine `StringReturnsCollection` -Funktion, die anhand einer Auflistung von Zeichenfolgen die zurückgegebenen Kontakte filtert.</span><span class="sxs-lookup"><span data-stu-id="d1b24-131">The following Entity SQL command defines a function `StringReturnsCollection` that takes a collection of strings to filter the returned contacts.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION2](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function2)]  
  
## <a name="see-also"></a><span data-ttu-id="d1b24-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1b24-132">See also</span></span>

- [<span data-ttu-id="d1b24-133">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="d1b24-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="d1b24-134">Entity SQL Language (Entity SQL-Sprache)</span><span class="sxs-lookup"><span data-stu-id="d1b24-134">Entity SQL Language</span></span>](entity-sql-language.md)
