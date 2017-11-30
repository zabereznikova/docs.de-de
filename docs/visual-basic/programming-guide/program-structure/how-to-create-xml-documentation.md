---
title: 'Gewusst wie: Erstellen einer XML-Dokumentation in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 63b6485de5aba2ca49d54a057045bec2062d12dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="be085-102">Gewusst wie: Erstellen einer XML-Dokumentation in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be085-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="be085-103">Dieses Beispiel zeigt, wie Sie XML-Dokumentationskommentare in den Code einfügen.</span><span class="sxs-lookup"><span data-stu-id="be085-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="be085-104">Zum Erstellen von XML-Dokumentation für einen Typ oder member</span><span class="sxs-lookup"><span data-stu-id="be085-104">To create XML documentation for a type or member</span></span>  
  
1.  <span data-ttu-id="be085-105">In der **Code-Editor**, positionieren Sie den Cursor in der Zeile oben den Typ oder Member, für die Sie Dokumentation erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="be085-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2.  <span data-ttu-id="be085-106">Typ `'''` (drei einfache Anführungszeichen).</span><span class="sxs-lookup"><span data-stu-id="be085-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="be085-107">Ein XML-Skelett für den Typ oder Member wird hinzugefügt, der **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="be085-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="be085-108">Fügen Sie beschreibende Informationen zwischen den entsprechenden Tags hinzu.</span><span class="sxs-lookup"><span data-stu-id="be085-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be085-109">Wenn Sie zusätzliche Zeilen innerhalb der XML-Dokumentation Block hinzufügen, muss jede Zeile mit beginnen `'''`.</span><span class="sxs-lookup"><span data-stu-id="be085-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4.  <span data-ttu-id="be085-110">Fügen Sie zusätzlichen Code, der den Typ oder Member mit dem neuen XML-Dokumentationskommentare verwendet.</span><span class="sxs-lookup"><span data-stu-id="be085-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="be085-111">IntelliSense zeigt den Text aus dem \<summary >-Tag für den Typ oder Member.</span><span class="sxs-lookup"><span data-stu-id="be085-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5.  <span data-ttu-id="be085-112">Kompilieren Sie den Code zum Generieren einer XML-Datei, die die Dokumentationskommentare enthält.</span><span class="sxs-lookup"><span data-stu-id="be085-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="be085-113">Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="be085-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be085-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be085-114">See Also</span></span>  
 [<span data-ttu-id="be085-115">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="be085-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="be085-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="be085-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [<span data-ttu-id="be085-117">/doc</span><span class="sxs-lookup"><span data-stu-id="be085-117">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
