---
title: Strukturierte Typen, die NULL-Werte zulassen (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ac7405aea459d51154ac25171bc76d637a94bf81
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="f1fe4-102">Strukturierte Typen, die NULL-Werte zulassen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f1fe4-102">Nullable Structured Types (Entity SQL)</span></span>
<span data-ttu-id="f1fe4-103">Eine `null`-Instanz eines strukturierten Typs ist eine Instanz, die nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f1fe4-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="f1fe4-104">Dies unterscheidet sich von einer vorhandenen Instanz, in der alle Eigenschaften den Wert `null` haben.</span><span class="sxs-lookup"><span data-stu-id="f1fe4-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="f1fe4-105">In diesem Thema werden strukturierte Typen beschrieben, die NULL-Werte zulassen. Zu dieser Beschreibung gehören eine Aufzählung der Typen, die NULL-Werte zulassen, und die Angabe von Codemustern, die `null`-Instanzen von strukturierten Typen erstellen, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="f1fe4-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="f1fe4-106">Arten strukturierter Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="f1fe4-106">Kinds of Nullable Structured Types</span></span>  
 <span data-ttu-id="f1fe4-107">Es gibt drei Arten von Strukturtypen, die NULL-Werte zulassen:</span><span class="sxs-lookup"><span data-stu-id="f1fe4-107">There are three kinds of nullable structure types:</span></span>  
  
-   <span data-ttu-id="f1fe4-108">Zeilentypen</span><span class="sxs-lookup"><span data-stu-id="f1fe4-108">Row types.</span></span>  
  
-   <span data-ttu-id="f1fe4-109">Komplexe Typen</span><span class="sxs-lookup"><span data-stu-id="f1fe4-109">Complex types.</span></span>  
  
-   <span data-ttu-id="f1fe4-110">Entitätstypen</span><span class="sxs-lookup"><span data-stu-id="f1fe4-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="f1fe4-111">Codemuster, die NULL-Instanzen strukturierter Typen erstellen</span><span class="sxs-lookup"><span data-stu-id="f1fe4-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  
 <span data-ttu-id="f1fe4-112">In den folgenden Szenarios werden `null`-Instanzen erstellt:</span><span class="sxs-lookup"><span data-stu-id="f1fe4-112">The following scenarios produce `null` instances:</span></span>  
  
-   <span data-ttu-id="f1fe4-113">`null` als strukturierten Typ formen:</span><span class="sxs-lookup"><span data-stu-id="f1fe4-113">Shaping `null` as a structured type:</span></span>  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   <span data-ttu-id="f1fe4-114">Umwandeln eines Basistyps in einen abgeleiteten Typ:</span><span class="sxs-lookup"><span data-stu-id="f1fe4-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   <span data-ttu-id="f1fe4-115">"Outer join on false"-Bedingung:</span><span class="sxs-lookup"><span data-stu-id="f1fe4-115">Outer join on false condition:</span></span>  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="f1fe4-116">--oder</span><span class="sxs-lookup"><span data-stu-id="f1fe4-116">--or</span></span>  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="f1fe4-117">--oder</span><span class="sxs-lookup"><span data-stu-id="f1fe4-117">--or</span></span>  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   <span data-ttu-id="f1fe4-118">Dereferenzierung eines `null`-Verweises:</span><span class="sxs-lookup"><span data-stu-id="f1fe4-118">Dereferencing a `null` reference:</span></span>  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   <span data-ttu-id="f1fe4-119">Abrufen von ANYELEMENT aus einer leeren Auflistung:</span><span class="sxs-lookup"><span data-stu-id="f1fe4-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   <span data-ttu-id="f1fe4-120">Überprüfen von Instanzen strukturierter Typen auf `null`:</span><span class="sxs-lookup"><span data-stu-id="f1fe4-120">Checking for `null` instances of structured types:</span></span>  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f1fe4-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1fe4-121">See Also</span></span>  
 [<span data-ttu-id="f1fe4-122">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f1fe4-122">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
