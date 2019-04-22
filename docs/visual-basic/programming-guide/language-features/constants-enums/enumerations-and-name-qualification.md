---
title: Enumerationen und Namensqualifikation (Visual Basic)
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
ms.openlocfilehash: f0a806b040720cf6682f8a72025a0590dd4d91f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818435"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a><span data-ttu-id="e957e-102">Enumerationen und Namensqualifikation (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e957e-102">Enumerations and Name Qualification (Visual Basic)</span></span>
<span data-ttu-id="e957e-103">Wenn auf einen Member einer Enumeration zu verweisen, müssen Sie normalerweise den Membernamen, durch den Enumerationsnamen qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="e957e-103">Normally, when referring to a member of an enumeration, you must qualify the member name with the enumeration name.</span></span> <span data-ttu-id="e957e-104">Beispielsweise zum Verweisen auf die `Sunday` Mitglied Ihrer `Days` Enumeration, verwenden Sie die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="e957e-104">For example, to refer to the `Sunday` member of your `Days` enumeration, you would use the following syntax:</span></span>  
  
 [!code-vb[VbEnumsTask#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#18)]  
  
## <a name="using-the-imports-statement"></a><span data-ttu-id="e957e-105">Verwenden der Importanweisung</span><span class="sxs-lookup"><span data-stu-id="e957e-105">Using the Imports Statement</span></span>  
 <span data-ttu-id="e957e-106">Sie können vermeiden, verwenden vollqualifizierte Namen durch das Hinzufügen einer `Imports` Anweisung, um die Namespace-Deklarationen-Abschnitt des Codes, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e957e-106">You can avoid using fully qualified names by adding an `Imports` statement to the namespace declarations section of your code, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 <span data-ttu-id="e957e-107">Ein `Imports` -Anweisung importiert Namespacenamen aus referenzierten Projekten und Assemblys, und aus dem gleichen Projekt wie das Modul, in dem die Anweisung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e957e-107">An `Imports` statement imports namespace names from referenced projects and assemblies and from within the same project as the module in which the statement appears.</span></span> <span data-ttu-id="e957e-108">Sobald diese Anweisung hinzugefügt wird, finden Sie in Ihrer Enumerationsmember ohne Qualifikation verwenden – wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e957e-108">Once this statement is added, you can refer to your enumeration members without qualification, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#24)]  
  
 <span data-ttu-id="e957e-109">Durch das Organisieren von Sätzen verknüpfter Konstanten in Enumerationen, können Sie den gleichen Namen für Aufzählungskonstanten in unterschiedlichen Kontexten.</span><span class="sxs-lookup"><span data-stu-id="e957e-109">By organizing sets of related constants in enumerations, you can use the same constant names in different contexts.</span></span> <span data-ttu-id="e957e-110">Beispielsweise können Sie die gleichen Namen für den Wochentagskonstanten in der `Days` und `WorkDays` Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="e957e-110">For example, you can use the same names for the weekday constants in the `Days` and `WorkDays` enumerations.</span></span> <span data-ttu-id="e957e-111">Bei Verwendung der `Imports` Anweisung für die Enumerationen, Sie müssen darauf achten, mehrdeutige Verweise zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e957e-111">If you use the `Imports` statement with your enumerations, you must be careful to avoid ambiguous references.</span></span> <span data-ttu-id="e957e-112">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e957e-112">Consider the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#25)]  
  
 <span data-ttu-id="e957e-113">Vorausgesetzt, dass `Monday` ist ein Mitglied sowohl der `Days` Enumeration und die `Workdays` Enumeration, die diesen Code wird ein Compilerfehler generiert.</span><span class="sxs-lookup"><span data-stu-id="e957e-113">Assuming that `Monday` is a member of both the `Days` enumeration and the `Workdays` enumeration, this code generates a compiler error.</span></span> <span data-ttu-id="e957e-114">Um mehrdeutige Verweise zu vermeiden, beim Verweisen auf einer einzelnen Konstante, qualifizieren Sie den Namen den Konstanten mit der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="e957e-114">To avoid ambiguous references when referring to an individual constant, qualify the constant name with its enumeration.</span></span> <span data-ttu-id="e957e-115">Der folgende Code bezieht sich auf die `Saturday` Konstanten in der `Days` und `WorkDays` Enumerationen.</span><span class="sxs-lookup"><span data-stu-id="e957e-115">The following code refers to the `Saturday` constants in the `Days` and `WorkDays` enumerations.</span></span>  
  
 [!code-vb[VbEnumsTask#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="e957e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e957e-116">See also</span></span>

- [<span data-ttu-id="e957e-117">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e957e-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="e957e-118">Vorgehensweise: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="e957e-118">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="e957e-119">Vorgehensweise: Finden Sie in einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="e957e-119">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="e957e-120">Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e957e-120">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="e957e-121">Vorgehensweise: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e957e-121">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="e957e-122">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e957e-122">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="e957e-123">Konstanten und literale Datentypen</span><span class="sxs-lookup"><span data-stu-id="e957e-123">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="e957e-124">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e957e-124">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="e957e-125">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="e957e-125">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="e957e-126">Datentypen</span><span class="sxs-lookup"><span data-stu-id="e957e-126">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
