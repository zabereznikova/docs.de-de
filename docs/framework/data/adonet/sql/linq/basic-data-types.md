---
title: Grundlegende Datentypen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: e88767bd478b4b59e8c395473cfd8a36aaf68f3b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="basic-data-types"></a><span data-ttu-id="222f3-102">Grundlegende Datentypen</span><span class="sxs-lookup"><span data-stu-id="222f3-102">Basic Data Types</span></span>
<span data-ttu-id="222f3-103">Da LINQ to SQL-Abfragen vor ihrer Ausführung auf dem Microsoft SQL Server in Transact-SQL übersetzt werden,</span><span class="sxs-lookup"><span data-stu-id="222f3-103">Because LINQ to SQL queries translate to Transact-SQL before they are executed on the Microsoft SQL Server.</span></span> <span data-ttu-id="222f3-104">unterstützt LINQ to SQL einen Großteil der integrierten Funktionen, die SQL Server für grundlegende Datentypen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="222f3-104">LINQ to SQL supports much of the same built-in functionality that SQL Server does for basic data types.</span></span>  
  
## <a name="casting"></a><span data-ttu-id="222f3-105">Umwandlung von Typen</span><span class="sxs-lookup"><span data-stu-id="222f3-105">Casting</span></span>  
 <span data-ttu-id="222f3-106">Implizite und explizite Umwandlungen von einem CLR-Quell- in einen CLR-Zieltyp werden unterstützt, wenn in SQL Server eine ähnliche gültige Konvertierung existiert.</span><span class="sxs-lookup"><span data-stu-id="222f3-106">Implicit or explicit casts are enabled from a source CLR type to a target CLR type if there is a similar valid conversion within SQL Server.</span></span> <span data-ttu-id="222f3-107">Weitere Informationen zu CLR-Umwandlung, finden Sie unter [CType-Funktion](~/docs/visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) und [als](~/docs/csharp/language-reference/keywords/as.md).</span><span class="sxs-lookup"><span data-stu-id="222f3-107">For more information about CLR casting, see [CType Function](~/docs/visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) and [as](~/docs/csharp/language-reference/keywords/as.md).</span></span> <span data-ttu-id="222f3-108">Nach der Konvertierung passen Varianten das Verhalten der durchgeführten Operationen für einen CLR-Ausdruck an das Verhalten anderer CLR-Ausdrücke an, die auf natürliche Weise dem Zieltyp zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="222f3-108">After conversion, casts change the behavior of operations performed on a CLR expression to match the behavior of other CLR expressions that naturally map to the destination type.</span></span> <span data-ttu-id="222f3-109">Umwandlungen sind auch im Kontext der Vererbungszuordnung übersetzbar.</span><span class="sxs-lookup"><span data-stu-id="222f3-109">Casts are also translatable in the context of inheritance mapping.</span></span> <span data-ttu-id="222f3-110">Objekte können in spezifischere Entitätsuntertypen umgewandelt werden, damit auf ihre untertypspezifischen Daten zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="222f3-110">Objects can be cast to more specific entity subtypes so that their subtype-specific data can be accessed.</span></span>  
  
## <a name="equality-operators"></a><span data-ttu-id="222f3-111">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="222f3-111">Equality Operators</span></span>  
 <span data-ttu-id="222f3-112">LINQ to SQL unterstützt die folgenden Gleichheitsoperatoren für grundlegende Datentypen in LINQ to SQL-Abfragen:</span><span class="sxs-lookup"><span data-stu-id="222f3-112">LINQ to SQL supports the following equality operators on basic data types inside LINQ to SQL queries:</span></span>  
  
-   <span data-ttu-id="222f3-113">Gleichheits- und Ungleichheitsoperator: Gleichheits- und Ungleichheitsoperatoren werden für numerische <xref:System.Boolean>-, <xref:System.DateTime>- und <xref:System.TimeSpan>-Typen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="222f3-113">Equal and Inequality Operator: Equality and inequality operators are supported for numeric <xref:System.Boolean>, <xref:System.DateTime>, and <xref:System.TimeSpan> types.</span></span> <span data-ttu-id="222f3-114">Weitere Informationen zu Visual Basic-Operatoren `=` und `<>`, finden Sie unter [Vergleichsoperatoren](~/docs/visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="222f3-114">For more about Visual Basic operators `=` and `<>`, see [Comparison Operators](~/docs/visual-basic/language-reference/operators/comparison-operators.md).</span></span> <span data-ttu-id="222f3-115">Weitere Informationen zu C#-Vergleichsoperatoren `==` und `!=`, finden Sie unter [==-Operator](~/docs/csharp/language-reference/operators/equality-comparison-operator.md) und [! =-Operator](~/docs/csharp/language-reference/operators/not-equal-operator.md)bzw.</span><span class="sxs-lookup"><span data-stu-id="222f3-115">For more information about C# comparison operators `==` and `!=`, see [== Operator](~/docs/csharp/language-reference/operators/equality-comparison-operator.md) and [!= Operator](~/docs/csharp/language-reference/operators/not-equal-operator.md), respectively</span></span>  
  
-   <span data-ttu-id="222f3-116">"Is"-Operator: Der `IS`-Operator verfügt über eine unterstützte Übersetzung, wenn Vererbungsmapping verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="222f3-116">Is operator: The `IS` operator has a supported translation when inheritance mapping is being used.</span></span> <span data-ttu-id="222f3-117">Er kann anstelle der direkten Prüfung der Diskriminatorspalte verwendet werden, um festzulegen, ob ein Objekt einen bestimmten Typ aufweist. Er wird in eine Prüfung der Diskriminatorspalte übersetzt.</span><span class="sxs-lookup"><span data-stu-id="222f3-117">It can be used instead of directly testing the discriminator column to determine whether an object is of a specific entity type, and is translated to a check on the discriminator column.</span></span> <span data-ttu-id="222f3-118">Weitere Informationen zu den Visual Basic- und C#-Operatoren finden Sie unter [Is Operator](~/docs/visual-basic/language-reference/operators/is-operator.md) und [ist](~/docs/csharp/language-reference/keywords/is.md).</span><span class="sxs-lookup"><span data-stu-id="222f3-118">For more information about the Visual Basic and C# Is operators, see [Is Operator](~/docs/visual-basic/language-reference/operators/is-operator.md) and [is](~/docs/csharp/language-reference/keywords/is.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="222f3-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="222f3-119">See Also</span></span>  
 [<span data-ttu-id="222f3-120">SQL-CLR-Typenzuordnung</span><span class="sxs-lookup"><span data-stu-id="222f3-120">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)  
 [<span data-ttu-id="222f3-121">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="222f3-121">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
