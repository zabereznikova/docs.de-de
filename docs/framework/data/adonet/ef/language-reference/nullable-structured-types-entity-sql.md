---
title: Strukturierte Typen, die NULL-Werte zulassen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: fc2230401ef98c005ab52a845de37482c0dcf698
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202263"
---
# <a name="nullable-structured-types-entity-sql"></a><span data-ttu-id="79f6b-102">Strukturierte Typen, die NULL-Werte zulassen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="79f6b-102">Nullable Structured Types (Entity SQL)</span></span>

<span data-ttu-id="79f6b-103">Eine `null`-Instanz eines strukturierten Typs ist eine Instanz, die nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="79f6b-103">A `null` instance of a structured type is an instance that does not exist.</span></span> <span data-ttu-id="79f6b-104">Dies unterscheidet sich von einer vorhandenen Instanz, in der alle Eigenschaften den Wert `null` haben.</span><span class="sxs-lookup"><span data-stu-id="79f6b-104">This is different from an existing instance in which all properties have `null` values.</span></span>  
  
 <span data-ttu-id="79f6b-105">In diesem Thema werden strukturierte Typen beschrieben, die NULL-Werte zulassen. Zu dieser Beschreibung gehören eine Aufzählung der Typen, die NULL-Werte zulassen, und die Angabe von Codemustern, die `null`-Instanzen von strukturierten Typen erstellen, die NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="79f6b-105">This topic describes the nullable structured types, including which types are nullable and which code patterns produce `null` instances of structured nullable types.</span></span>  
  
## <a name="kinds-of-nullable-structured-types"></a><span data-ttu-id="79f6b-106">Arten strukturierter Typen, die NULL-Werte zulassen</span><span class="sxs-lookup"><span data-stu-id="79f6b-106">Kinds of Nullable Structured Types</span></span>  

 <span data-ttu-id="79f6b-107">Es gibt drei Arten von Strukturtypen, die NULL-Werte zulassen:</span><span class="sxs-lookup"><span data-stu-id="79f6b-107">There are three kinds of nullable structure types:</span></span>  
  
- <span data-ttu-id="79f6b-108">Zeilentypen</span><span class="sxs-lookup"><span data-stu-id="79f6b-108">Row types.</span></span>  
  
- <span data-ttu-id="79f6b-109">Komplexe Typen</span><span class="sxs-lookup"><span data-stu-id="79f6b-109">Complex types.</span></span>  
  
- <span data-ttu-id="79f6b-110">Entitätstypen</span><span class="sxs-lookup"><span data-stu-id="79f6b-110">Entity types.</span></span>  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a><span data-ttu-id="79f6b-111">Codemuster, die NULL-Instanzen strukturierter Typen erstellen</span><span class="sxs-lookup"><span data-stu-id="79f6b-111">Code Patterns that Produce Null Instances of Structured Types</span></span>  

 <span data-ttu-id="79f6b-112">In den folgenden Szenarios werden `null`-Instanzen erstellt:</span><span class="sxs-lookup"><span data-stu-id="79f6b-112">The following scenarios produce `null` instances:</span></span>  
  
- <span data-ttu-id="79f6b-113">`null` als strukturierten Typ formen:</span><span class="sxs-lookup"><span data-stu-id="79f6b-113">Shaping `null` as a structured type:</span></span>  
  
    ```sql  
    TREAT (NULL AS StructuredType)  
    ```  
  
- <span data-ttu-id="79f6b-114">Umwandeln eines Basistyps in einen abgeleiteten Typ:</span><span class="sxs-lookup"><span data-stu-id="79f6b-114">Upcasting of a base type to a derived type:</span></span>  
  
    ```sql  
    TREAT (BaseType AS DerivedType)  
    ```  
  
- <span data-ttu-id="79f6b-115">"Outer join on false"-Bedingung:</span><span class="sxs-lookup"><span data-stu-id="79f6b-115">Outer join on false condition:</span></span>  
  
    ```sql  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="79f6b-116">--oder</span><span class="sxs-lookup"><span data-stu-id="79f6b-116">--or</span></span>  
  
    ```sql  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     <span data-ttu-id="79f6b-117">--oder</span><span class="sxs-lookup"><span data-stu-id="79f6b-117">--or</span></span>  
  
    ```sql  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
- <span data-ttu-id="79f6b-118">Dereferenzierung eines `null`-Verweises:</span><span class="sxs-lookup"><span data-stu-id="79f6b-118">Dereferencing a `null` reference:</span></span>  
  
    ```sql  
    DEREF(NullRef)  
    ```  
  
- <span data-ttu-id="79f6b-119">Abrufen von ANYELEMENT aus einer leeren Auflistung:</span><span class="sxs-lookup"><span data-stu-id="79f6b-119">Obtaining ANYELEMENT from an empty collection:</span></span>  
  
    ```sql  
    ANYELEMENT(EmptyCollection)  
    ```  
  
- <span data-ttu-id="79f6b-120">Überprüfen von Instanzen strukturierter Typen auf `null`:</span><span class="sxs-lookup"><span data-stu-id="79f6b-120">Checking for `null` instances of structured types:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="79f6b-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79f6b-121">See also</span></span>

- [<span data-ttu-id="79f6b-122">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="79f6b-122">Entity SQL Overview</span></span>](entity-sql-overview.md)
