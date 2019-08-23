---
title: 'Vorgehensweise: Erstellen einer XML-Dokumentation in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 9380c23ab6cfdbecd519926229b45ed863f07f9e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947714"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="0137f-102">Vorgehensweise: Erstellen einer XML-Dokumentation in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0137f-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="0137f-103">Dieses Beispiel zeigt, wie Sie Ihrem Code XML-Dokumentations Kommentare hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0137f-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="0137f-104">So erstellen Sie eine XML-Dokumentation für einen Typ oder Member</span><span class="sxs-lookup"><span data-stu-id="0137f-104">To create XML documentation for a type or member</span></span>  
  
1. <span data-ttu-id="0137f-105">Positionieren Sie den Cursor im **Code-Editor**in der Zeile oberhalb des Typs oder Members, für den Sie eine Dokumentation erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0137f-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2. <span data-ttu-id="0137f-106">Type `'''` (drei einfache Anführungszeichen).</span><span class="sxs-lookup"><span data-stu-id="0137f-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="0137f-107">Ein XML-Gerüst für den Typ oder Member wird im **Code-Editor**hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0137f-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3. <span data-ttu-id="0137f-108">Fügen Sie beschreibende Informationen zwischen den entsprechenden Tags hinzu.</span><span class="sxs-lookup"><span data-stu-id="0137f-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0137f-109">Wenn Sie im XML-Dokumentationsblock weitere Zeilen hinzufügen, muss jede Zeile mit `'''`beginnen.</span><span class="sxs-lookup"><span data-stu-id="0137f-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4. <span data-ttu-id="0137f-110">Fügen Sie zusätzlichen Code hinzu, der den Typ oder Member mit den neuen XML-Dokumentations Kommentaren verwendet.</span><span class="sxs-lookup"><span data-stu-id="0137f-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="0137f-111">IntelliSense zeigt den Text aus dem \<Zusammenfassungs >-Tag für den Typ oder Member an.</span><span class="sxs-lookup"><span data-stu-id="0137f-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5. <span data-ttu-id="0137f-112">Kompilieren Sie den Code, um eine XML-Datei zu generieren, die die Dokumentations Kommentare enthält.</span><span class="sxs-lookup"><span data-stu-id="0137f-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="0137f-113">Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="0137f-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0137f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0137f-114">See also</span></span>

- [<span data-ttu-id="0137f-115">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="0137f-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="0137f-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="0137f-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
- [<span data-ttu-id="0137f-117">/doc</span><span class="sxs-lookup"><span data-stu-id="0137f-117">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
