---
title: Enumerationen und Namensqualifikation
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
ms.openlocfilehash: 6e067d72e557b97f8626b148e173e3d1583f92b8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086269"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a><span data-ttu-id="e1829-102">Enumerationen und Namensqualifikation (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1829-102">Enumerations and Name Qualification (Visual Basic)</span></span>

<span data-ttu-id="e1829-103">Normalerweise müssen Sie beim Verweisen auf einen Member einer Enumeration den Elementnamen mit dem Enumerationsnamen qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="e1829-103">Normally, when referring to a member of an enumeration, you must qualify the member name with the enumeration name.</span></span> <span data-ttu-id="e1829-104">Wenn Sie z. b. auf das- `Sunday` Member der- `Days` Enumeration verweisen möchten, verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="e1829-104">For example, to refer to the `Sunday` member of your `Days` enumeration, you would use the following syntax:</span></span>  
  
 [!code-vb[VbEnumsTask#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#18)]  
  
## <a name="using-the-imports-statement"></a><span data-ttu-id="e1829-105">Verwenden der Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e1829-105">Using the Imports Statement</span></span>  

 <span data-ttu-id="e1829-106">Sie können die Verwendung voll qualifizierter Namen vermeiden, indem Sie `Imports` dem Abschnitt Namespace Deklarationen in Ihrem Code eine-Anweisung hinzufügen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e1829-106">You can avoid using fully qualified names by adding an `Imports` statement to the namespace declarations section of your code, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 <span data-ttu-id="e1829-107">Eine `Imports` -Anweisung importiert Namespace Namen aus referenzierten Projekten und Assemblys und innerhalb desselben Projekts wie das Modul, in dem die-Anweisung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e1829-107">An `Imports` statement imports namespace names from referenced projects and assemblies and from within the same project as the module in which the statement appears.</span></span> <span data-ttu-id="e1829-108">Nachdem diese Anweisung hinzugefügt wurde, können Sie ohne Qualifizierung auf Ihre Enumerationsmember verweisen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e1829-108">Once this statement is added, you can refer to your enumeration members without qualification, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#24)]  
  
 <span data-ttu-id="e1829-109">Wenn Sie Sätze verwandter Konstanten in Enumerationen organisieren, können Sie dieselben Konstanten Namen in unterschiedlichen Kontexten verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1829-109">By organizing sets of related constants in enumerations, you can use the same constant names in different contexts.</span></span> <span data-ttu-id="e1829-110">Beispielsweise können Sie in den `Days` Enumerationen und die gleichen Namen für die Wochentag-Konstanten verwenden `WorkDays` .</span><span class="sxs-lookup"><span data-stu-id="e1829-110">For example, you can use the same names for the weekday constants in the `Days` and `WorkDays` enumerations.</span></span> <span data-ttu-id="e1829-111">Wenn Sie die- `Imports` Anweisung mit ihren Enumerationen verwenden, müssen Sie darauf achten, mehrdeutige Verweise zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e1829-111">If you use the `Imports` statement with your enumerations, you must be careful to avoid ambiguous references.</span></span> <span data-ttu-id="e1829-112">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e1829-112">Consider the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#25)]  
  
 <span data-ttu-id="e1829-113">Wenn Sie davon ausgehen, dass `Monday` ein Member der `Days` -Enumeration und der- `Workdays` Enumeration ist, generiert dieser Code einen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="e1829-113">Assuming that `Monday` is a member of both the `Days` enumeration and the `Workdays` enumeration, this code generates a compiler error.</span></span> <span data-ttu-id="e1829-114">Um mehrdeutige Verweise zu vermeiden, wenn Sie auf eine einzelne Konstante verweisen, qualifizieren Sie den konstanten Namen durch seine Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e1829-114">To avoid ambiguous references when referring to an individual constant, qualify the constant name with its enumeration.</span></span> <span data-ttu-id="e1829-115">Der folgende Code bezieht sich auf die `Saturday` Konstanten in `Days` den `WorkDays` Enumerationen und.</span><span class="sxs-lookup"><span data-stu-id="e1829-115">The following code refers to the `Saturday` constants in the `Days` and `WorkDays` enumerations.</span></span>  
  
 [!code-vb[VbEnumsTask#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="e1829-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1829-116">See also</span></span>

- [<span data-ttu-id="e1829-117">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e1829-117">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="e1829-118">Gewusst wie: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="e1829-118">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="e1829-119">Vorgehensweise: Verweisen auf einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="e1829-119">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="e1829-120">Gewusst wie: Durchlaufen einer Enumeration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1829-120">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="e1829-121">Vorgehensweise: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e1829-121">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="e1829-122">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e1829-122">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="e1829-123">Konstanten und literale Datentypen</span><span class="sxs-lookup"><span data-stu-id="e1829-123">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="e1829-124">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e1829-124">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
- [<span data-ttu-id="e1829-125">Imports-Anweisung (.NET-Namespace und Typ)</span><span class="sxs-lookup"><span data-stu-id="e1829-125">Imports Statement (.NET Namespace and Type)</span></span>](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="e1829-126">Datentypen</span><span class="sxs-lookup"><span data-stu-id="e1829-126">Data Types</span></span>](../../../language-reference/data-types/index.md)
