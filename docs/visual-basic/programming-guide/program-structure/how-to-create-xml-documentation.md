---
title: 'Gewusst wie: Erstellen von XML-Dokumentation in Visual Basic | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML comments
- XML documentation, creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 3171877f4fa1913b5535d71d671cea97b5a22850
ms.contentlocale: de-de
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="98609-102">Gewusst wie: Erstellen einer XML-Dokumentation in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="98609-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="98609-103">Dieses Beispiel zeigt, wie Sie XML-Dokumentationskommentare in den Code einfügen.</span><span class="sxs-lookup"><span data-stu-id="98609-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="98609-104">Erstellen von XML-Dokumentation für einen Typ oder member</span><span class="sxs-lookup"><span data-stu-id="98609-104">To create XML documentation for a type or member</span></span>  
  
1.  <span data-ttu-id="98609-105">In der **Code-Editor**, positionieren Sie den Cursor in die Zeile über den Typ oder Member, für die Sie Dokumentation erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="98609-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2.  <span data-ttu-id="98609-106">Typ `'''` (drei einfache Anführungszeichen).</span><span class="sxs-lookup"><span data-stu-id="98609-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="98609-107">Ein XML-Skelett für den Typ oder Member wird hinzugefügt, der **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="98609-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="98609-108">Fügen Sie beschreibende Informationen zwischen den entsprechenden Tags hinzu.</span><span class="sxs-lookup"><span data-stu-id="98609-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="98609-109">Wenn Sie zusätzliche Zeilen innerhalb der XML-Dokumentation Block hinzufügen, muss jede Zeile beginnen Sie mit `'''`.</span><span class="sxs-lookup"><span data-stu-id="98609-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4.  <span data-ttu-id="98609-110">Fügen Sie zusätzlichen Code, der den Typ oder Member mit dem neuen XML-Dokumentationskommentaren verwendet.</span><span class="sxs-lookup"><span data-stu-id="98609-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="98609-111">IntelliSense zeigt den Text aus der \<Zusammenfassung > Tag für den Typ oder Member.</span><span class="sxs-lookup"><span data-stu-id="98609-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5.  <span data-ttu-id="98609-112">Kompilieren Sie den Code zum Generieren einer XML-Datei, die die Dokumentationskommentare enthält.</span><span class="sxs-lookup"><span data-stu-id="98609-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="98609-113">Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="98609-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98609-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98609-114">See Also</span></span>  
 <span data-ttu-id="98609-115">[Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span><span class="sxs-lookup"><span data-stu-id="98609-115">[Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span></span>  
<span data-ttu-id="98609-116"> [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span><span class="sxs-lookup"><span data-stu-id="98609-116"> [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span></span>  
<span data-ttu-id="98609-117"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)</span><span class="sxs-lookup"><span data-stu-id="98609-117"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)</span></span>
