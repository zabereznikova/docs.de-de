---
title: Strukturierte Typen, die NULL-Werte zulassen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: 632b092e1d0d99a2a40cc3cd4b323e234de6232b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760323"
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="4a17f-102">Strukturierte Typen, die NULL-Werte zulassen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4a17f-102">Nullable Structured Types (Entity SQL)</span></span>
<span data-ttu-id="4a17f-103">Eine `null`-Instanz eines strukturierten Typs ist eine Instanz, die nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4a17f-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="4a17f-104">Dies unterscheidet sich von einer vorhandenen Instanz, in der alle Eigenschaften den Wert `null` haben.</span><span class="sxs-lookup"><span data-stu-id="4a17f-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="4a17f-105">In diesem Thema werden strukturierte Typen beschrieben, die NULL-Werte zulassen. Zu dieser Beschreibung gehören eine Aufzählung der Typen, die NULL-Werte zulassen, und die Angabe von Codemustern, die `null`-Instanzen von strukturierten Typen erstellen, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="4a17f-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="4a17f-106">Arten strukturierter Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="4a17f-106">Kinds of Nullable Structured Types</span></span>  
 <span data-ttu-id="4a17f-107">Es gibt drei Arten von Strukturtypen, die NULL-Werte zulassen:</span><span class="sxs-lookup"><span data-stu-id="4a17f-107">There are three kinds of nullable structure types:</span></span>  
  
- <span data-ttu-id="4a17f-108">Zeilentypen</span><span class="sxs-lookup"><span data-stu-id="4a17f-108">Row types.</span></span>  
  
- <span data-ttu-id="4a17f-109">Komplexe Typen</span><span class="sxs-lookup"><span data-stu-id="4a17f-109">Complex types.</span></span>  
  
- <span data-ttu-id="4a17f-110">Entitätstypen</span><span class="sxs-lookup"><span data-stu-id="4a17f-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="4a17f-111">Codemuster, die NULL-Instanzen strukturierter Typen erstellen</span><span class="sxs-lookup"><span data-stu-id="4a17f-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  
 <span data-ttu-id="4a17f-112">In den folgenden Szenarios werden `null`-Instanzen erstellt:</span><span class="sxs-lookup"><span data-stu-id="4a17f-112">The following scenarios produce `null` instances:</span></span>  
  
- <span data-ttu-id="4a17f-113">`null` als strukturierten Typ formen:</span><span class="sxs-lookup"><span data-stu-id="4a17f-113">Shaping `null` as a structured type:</span></span>  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
- <span data-ttu-id="4a17f-114">Umwandeln eines Basistyps in einen abgeleiteten Typ:</span><span class="sxs-lookup"><span data-stu-id="4a17f-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
- <span data-ttu-id="4a17f-115">"Outer join on false"-Bedingung:</span><span class="sxs-lookup"><span data-stu-id="4a17f-115">Outer join on false condition:</span></span>  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="4a17f-116">--oder</span><span class="sxs-lookup"><span data-stu-id="4a17f-116">--or</span></span>  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="4a17f-117">--oder</span><span class="sxs-lookup"><span data-stu-id="4a17f-117">--or</span></span>  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
- <span data-ttu-id="4a17f-118">Dereferenzierung eines `null`-Verweises:</span><span class="sxs-lookup"><span data-stu-id="4a17f-118">Dereferencing a `null` reference:</span></span>  
  
    ```  
    DEREF(NullRef)  
    ```  
  
- <span data-ttu-id="4a17f-119">Abrufen von ANYELEMENT aus einer leeren Auflistung:</span><span class="sxs-lookup"><span data-stu-id="4a17f-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
- <span data-ttu-id="4a17f-120">Überprüfen von Instanzen strukturierter Typen auf `null`:</span><span class="sxs-lookup"><span data-stu-id="4a17f-120">Checking for `null` instances of structured types:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4a17f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a17f-121">See also</span></span>

- [<span data-ttu-id="4a17f-122">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="4a17f-122">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
