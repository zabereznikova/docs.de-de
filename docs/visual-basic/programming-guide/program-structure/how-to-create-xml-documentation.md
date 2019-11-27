---
title: 'Gewusst wie: Erstellen einer XML-Dokumentation'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 41b7ef1f435fd0a4f20c4ca2936e2d91e155f7c5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347424"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="1c490-102">Gewusst wie: Erstellen einer XML-Dokumentation in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1c490-102">How to: Create XML Documentation in Visual Basic</span></span>

<span data-ttu-id="1c490-103">Dieses Beispiel zeigt, wie Sie Ihrem Code XML-Dokumentations Kommentare hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1c490-103">This example shows how to add XML documentation comments to your code.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="1c490-104">So erstellen Sie eine XML-Dokumentation für einen Typ oder Member</span><span class="sxs-lookup"><span data-stu-id="1c490-104">To create XML documentation for a type or member</span></span>

1. <span data-ttu-id="1c490-105">Positionieren Sie den Cursor im **Code-Editor**in der Zeile oberhalb des Typs oder Members, für den Sie eine Dokumentation erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1c490-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>

2. <span data-ttu-id="1c490-106">Geben Sie `'''` (drei einfache Anführungszeichen) ein.</span><span class="sxs-lookup"><span data-stu-id="1c490-106">Type `'''` (three single-quotation marks).</span></span>

    <span data-ttu-id="1c490-107">Ein XML-Gerüst für den Typ oder Member wird im **Code-Editor**hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1c490-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>

3. <span data-ttu-id="1c490-108">Fügen Sie beschreibende Informationen zwischen den entsprechenden Tags hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c490-108">Add descriptive information between the appropriate tags.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1c490-109">Wenn Sie im XML-Dokumentationsblock weitere Zeilen hinzufügen, muss jede Zeile mit `'''`beginnen.</span><span class="sxs-lookup"><span data-stu-id="1c490-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>

4. <span data-ttu-id="1c490-110">Fügen Sie zusätzlichen Code hinzu, der den Typ oder Member mit den neuen XML-Dokumentations Kommentaren verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c490-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>

    <span data-ttu-id="1c490-111">IntelliSense zeigt den Text aus der \<Zusammenfassungs >-Tags für den Typ oder Member an.</span><span class="sxs-lookup"><span data-stu-id="1c490-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>

5. <span data-ttu-id="1c490-112">Kompilieren Sie den Code, um eine XML-Datei zu generieren, die die Dokumentations Kommentare enthält.</span><span class="sxs-lookup"><span data-stu-id="1c490-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="1c490-113">Weitere Informationen finden Sie unter [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="1c490-113">For more information, see [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1c490-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c490-114">See also</span></span>

- [<span data-ttu-id="1c490-115">Dokumentieren von Code mit XML</span><span class="sxs-lookup"><span data-stu-id="1c490-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="1c490-116">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="1c490-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
- [<span data-ttu-id="1c490-117">-doc</span><span class="sxs-lookup"><span data-stu-id="1c490-117">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
