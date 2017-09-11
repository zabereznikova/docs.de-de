---
title: Verarbeiten der XML-Datei (Visual Basic) | Microsoft-Dokumentation
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
- XML comments, parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: cf15cf59413e0e019086dd1a79951ccb212f037b
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="processing-the-xml-file-visual-basic"></a><span data-ttu-id="065ec-102">Verarbeiten der XML-Datei (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="065ec-102">Processing the XML File (Visual Basic)</span></span>
<span data-ttu-id="065ec-103">Der Compiler generiert eine ID-Zeichenfolge für jedes Konstrukt in Ihrem Code, der zum Generieren von Dokumentation gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="065ec-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="065ec-104">(Informationen zum Markieren von Code finden Sie unter [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) Die ID-Zeichenfolge identifiziert eindeutig das Konstrukt.</span><span class="sxs-lookup"><span data-stu-id="065ec-104">(For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="065ec-105">Programme, die die XML-Datei verarbeiten können die ID-Zeichenfolge zum Identifizieren der entsprechenden [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Metadaten/Reflektion-Element.</span><span class="sxs-lookup"><span data-stu-id="065ec-105">Programs that process the XML file can use the ID string to identify the corresponding [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] metadata/reflection item.</span></span>  
  
 <span data-ttu-id="065ec-106">Die XML-Datei ist keine hierarchische Darstellung des Codes. Es ist eine flache Liste mit einer generierten ID für jedes Element.</span><span class="sxs-lookup"><span data-stu-id="065ec-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span></span>  
  
 <span data-ttu-id="065ec-107">Der Compiler verwendet die folgenden Regeln beim Generieren der ID-Zeichenfolgen:</span><span class="sxs-lookup"><span data-stu-id="065ec-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
-   <span data-ttu-id="065ec-108">In der Zeichenfolge wird kein Leerzeichen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="065ec-108">No white space is placed in the string.</span></span>  
  
-   <span data-ttu-id="065ec-109">Der erste Teil der ID-Zeichenfolge kennzeichnet die Art des Elements identifiziert werden, durch ein einzelnes Zeichen, gefolgt von einem Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="065ec-109">The first part of the ID string identifies the kind of member being identified, with a single character followed by a colon.</span></span> <span data-ttu-id="065ec-110">Die folgenden Membertypen werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="065ec-110">The following member types are used.</span></span>  
  
|<span data-ttu-id="065ec-111">Zeichen</span><span class="sxs-lookup"><span data-stu-id="065ec-111">Character</span></span>|<span data-ttu-id="065ec-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="065ec-112">Description</span></span>|  
|---|---|  
|<span data-ttu-id="065ec-113">N</span><span class="sxs-lookup"><span data-stu-id="065ec-113">N</span></span>|<span data-ttu-id="065ec-114">namespace</span><span class="sxs-lookup"><span data-stu-id="065ec-114">namespace</span></span><br /><br /> <span data-ttu-id="065ec-115">Ein Namespace können keine Dokumentationskommentare hinzugefügt, Sie können jedoch CREF-Verweise, sofern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="065ec-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span></span>|  
|<span data-ttu-id="065ec-116">T</span><span class="sxs-lookup"><span data-stu-id="065ec-116">T</span></span>|<span data-ttu-id="065ec-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`,`Delegate`</span><span class="sxs-lookup"><span data-stu-id="065ec-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span></span>|  
|<span data-ttu-id="065ec-118">F</span><span class="sxs-lookup"><span data-stu-id="065ec-118">F</span></span>|<span data-ttu-id="065ec-119">Feld:`Dim`</span><span class="sxs-lookup"><span data-stu-id="065ec-119">field: `Dim`</span></span>|  
|<span data-ttu-id="065ec-120">P</span><span class="sxs-lookup"><span data-stu-id="065ec-120">P</span></span>|<span data-ttu-id="065ec-121">Eigenschaft: `Property` (einschließlich Standardeigenschaften)</span><span class="sxs-lookup"><span data-stu-id="065ec-121">property: `Property` (including default properties)</span></span>|  
|<span data-ttu-id="065ec-122">M</span><span class="sxs-lookup"><span data-stu-id="065ec-122">M</span></span>|<span data-ttu-id="065ec-123">method: `Sub`, `Function`, `Declare`,`Operator`</span><span class="sxs-lookup"><span data-stu-id="065ec-123">method: `Sub`, `Function`, `Declare`, `Operator`</span></span>|  
|<span data-ttu-id="065ec-124">E</span><span class="sxs-lookup"><span data-stu-id="065ec-124">E</span></span>|<span data-ttu-id="065ec-125">Ereignis:`Event`</span><span class="sxs-lookup"><span data-stu-id="065ec-125">event: `Event`</span></span>|  
|<span data-ttu-id="065ec-126">!</span><span class="sxs-lookup"><span data-stu-id="065ec-126">!</span></span>|<span data-ttu-id="065ec-127">Fehlerzeichenfolge</span><span class="sxs-lookup"><span data-stu-id="065ec-127">error string</span></span><br /><br /> <span data-ttu-id="065ec-128">Der Rest der Zeichenfolge enthält Informationen über den Fehler.</span><span class="sxs-lookup"><span data-stu-id="065ec-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="065ec-129">Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler werden Fehlerinformationen für Links, die nicht aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="065ec-129">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler generates error information for links that cannot be resolved.</span></span>|  
  
-   <span data-ttu-id="065ec-130">Der zweite Teil der `String` ist der vollqualifizierte Name des Elements, beginnend mit dem Stamm des Namespace.</span><span class="sxs-lookup"><span data-stu-id="065ec-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="065ec-131">Der Name des Elements, seiner einschließenden Typen und der Namespace sind durch Punkte getrennt.</span><span class="sxs-lookup"><span data-stu-id="065ec-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span></span> <span data-ttu-id="065ec-132">Wenn der Name des Elements selbst Punkte enthält, werden sie ersetzt durch ein Nummernzeichen (#).</span><span class="sxs-lookup"><span data-stu-id="065ec-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span></span> <span data-ttu-id="065ec-133">Es wird vorausgesetzt, dass kein Element ein Nummernzeichen direkt im Namen aufweist.</span><span class="sxs-lookup"><span data-stu-id="065ec-133">It is assumed that no item has a number sign directly in its name.</span></span> <span data-ttu-id="065ec-134">Z. B. den vollqualifizierten Namen von der `String` Konstruktor wäre `System.String.#ctor`.</span><span class="sxs-lookup"><span data-stu-id="065ec-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span></span>  
  
-   <span data-ttu-id="065ec-135">Eigenschaften und Methoden sind die Argumente der Methode folgt die Argumentliste in Klammern eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="065ec-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="065ec-136">Wenn keine Argumente vorhanden sind, werden keine Klammern verwendet.</span><span class="sxs-lookup"><span data-stu-id="065ec-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="065ec-137">Die Argumente werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="065ec-137">The arguments are separated by commas.</span></span> <span data-ttu-id="065ec-138">Die Codierung jedes Arguments erfolgt genauso wie es in ist eine [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Signatur.</span><span class="sxs-lookup"><span data-stu-id="065ec-138">The encoding of each argument follows directly how it is encoded in a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] signature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="065ec-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="065ec-139">Example</span></span>  
 <span data-ttu-id="065ec-140">Der folgende Code zeigt, wie die ID-Zeichenfolgen für eine Klasse und ihre Member generiert.</span><span class="sxs-lookup"><span data-stu-id="065ec-140">The following code shows how the ID strings for a class and its members are generated.</span></span>  
  
 <span data-ttu-id="065ec-141">[!code-vb[VbVbcnXmlDocComments&#10;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="065ec-141">[!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="065ec-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="065ec-142">See Also</span></span>  
 <span data-ttu-id="065ec-143">[/ doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span><span class="sxs-lookup"><span data-stu-id="065ec-143">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span></span>  
<span data-ttu-id="065ec-144"> [Gewusst wie: Erstellen einer XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span><span class="sxs-lookup"><span data-stu-id="065ec-144"> [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span></span>
