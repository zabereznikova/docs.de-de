---
title: 'Gewusst wie: Erstellen einer XML-Dokumentation in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 3dfec94a3dd1b8da5d371529b91b47f018bb3843
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43422428"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="2b3e9-102">Gewusst wie: Erstellen einer XML-Dokumentation in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2b3e9-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="2b3e9-103">Dieses Beispiel zeigt, wie Sie XML-Dokumentationskommentare zu Ihrem Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2b3e9-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="2b3e9-104">Um XML-Dokumentation für einen Typ oder Member zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2b3e9-104">To create XML documentation for a type or member</span></span>  
  
1.  <span data-ttu-id="2b3e9-105">In der **Code-Editor**, positionieren Sie den Cursor in die Zeile über den Typ oder Member, für die Erstellung der Dokumentation werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2b3e9-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2.  <span data-ttu-id="2b3e9-106">Typ `'''` (drei einfache Anführungszeichen).</span><span class="sxs-lookup"><span data-stu-id="2b3e9-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="2b3e9-107">Ein XML-Gerüst für den Typ oder Member hinzugefügt wird, die **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="2b3e9-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="2b3e9-108">Hinzufügen von beschreibenden Informationen zwischen den entsprechenden Tags.</span><span class="sxs-lookup"><span data-stu-id="2b3e9-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b3e9-109">Wenn Sie zusätzliche Zeilen innerhalb des Blocks des XML-Dokumentation hinzufügen, muss jede Zeile mit beginnen `'''`.</span><span class="sxs-lookup"><span data-stu-id="2b3e9-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4.  <span data-ttu-id="2b3e9-110">Fügen Sie zusätzlichen Code, der den Typ oder Member mit dem neuen XML-Dokumentationskommentaren verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b3e9-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="2b3e9-111">IntelliSense zeigt den Text aus der \<summary >-Tag für den Typ oder Member.</span><span class="sxs-lookup"><span data-stu-id="2b3e9-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5.  <span data-ttu-id="2b3e9-112">Kompilieren Sie den Code zum Generieren einer XML-Datei, die die Dokumentationskommentare enthält.</span><span class="sxs-lookup"><span data-stu-id="2b3e9-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="2b3e9-113">Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="2b3e9-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b3e9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b3e9-114">See Also</span></span>  
 [<span data-ttu-id="2b3e9-115">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="2b3e9-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="2b3e9-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="2b3e9-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)  
 [<span data-ttu-id="2b3e9-117">/doc</span><span class="sxs-lookup"><span data-stu-id="2b3e9-117">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
