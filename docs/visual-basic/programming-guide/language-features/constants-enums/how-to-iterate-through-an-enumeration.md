---
title: 'Vorgehensweise: Durchlaufen einer Enumeration'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 21c170d4708b90987a3f1e9c18969b8803fcdbe0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058715"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a><span data-ttu-id="054a5-102">Gewusst wie: Durchlaufen einer Enumeration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="054a5-102">How to: Iterate Through An Enumeration in Visual Basic</span></span>

<span data-ttu-id="054a5-103">Durch Enumerationen wird ein bequemer Weg bereitgestellt, um mit Sätzen verknüpfter Konstanten zu arbeiten, und um konstanten Werten Namen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="054a5-103">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="054a5-104">Um eine Enumeration zu durchlaufen, können Sie Sie mithilfe der-Methode in ein Array verschieben <xref:System.Enum.GetValues%2A> .</span><span class="sxs-lookup"><span data-stu-id="054a5-104">To iterate through an enumeration, you can move it into an array using the <xref:System.Enum.GetValues%2A> method.</span></span> <span data-ttu-id="054a5-105">Sie können auch eine Enumeration mithilfe einer-Anweisung durchlaufen, indem Sie die- `For...Each` oder-Methode verwenden, <xref:System.Enum.GetNames%2A> <xref:System.Enum.GetValues%2A> um die Zeichenfolge oder den numerischen Wert zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="054a5-105">You could also iterate through an enumeration using a `For...Each` statement, using the <xref:System.Enum.GetNames%2A> or <xref:System.Enum.GetValues%2A> method to extract the string or numeric value.</span></span>  
  
### <a name="to-iterate-through-an-enumeration"></a><span data-ttu-id="054a5-106">So durchlaufen Sie eine Enumeration</span><span class="sxs-lookup"><span data-stu-id="054a5-106">To iterate through an enumeration</span></span>  
  
- <span data-ttu-id="054a5-107">Deklarieren Sie ein Array, und konvertieren Sie die Enumeration mit der- <xref:System.Enum.GetValues%2A> Methode, bevor Sie das Array wie jede andere Variable übergeben.</span><span class="sxs-lookup"><span data-stu-id="054a5-107">Declare an array and convert the enumeration to it with the <xref:System.Enum.GetValues%2A> method before passing the array as you would any other variable.</span></span> <span data-ttu-id="054a5-108">Im folgenden Beispiel werden die einzelnen Member der-Enumeration beim <xref:Microsoft.VisualBasic.FirstDayOfWeek> durchlaufen der-Enumeration angezeigt.</span><span class="sxs-lookup"><span data-stu-id="054a5-108">The following example displays each member of the enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> as it iterates through the enumeration.</span></span>  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="054a5-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="054a5-109">See also</span></span>

- [<span data-ttu-id="054a5-110">Übersicht über Enumerationen</span><span class="sxs-lookup"><span data-stu-id="054a5-110">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="054a5-111">Gewusst wie: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="054a5-111">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="054a5-112">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="054a5-112">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="054a5-113">Vorgehensweise: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="054a5-113">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="054a5-114">Vorgehensweise: Verweisen auf einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="054a5-114">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="054a5-115">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="054a5-115">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="054a5-116">Arrays</span><span class="sxs-lookup"><span data-stu-id="054a5-116">Arrays</span></span>](../arrays/index.md)
