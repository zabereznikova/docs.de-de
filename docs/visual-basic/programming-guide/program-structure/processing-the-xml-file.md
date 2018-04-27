---
title: Verarbeiten der XML-Datei (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 86dae99f2d17a506a27cf491a76083df618ba27b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="processing-the-xml-file-visual-basic"></a><span data-ttu-id="1e64d-102">Verarbeiten der XML-Datei (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e64d-102">Processing the XML File (Visual Basic)</span></span>
<span data-ttu-id="1e64d-103">Für jedes Konstrukt, das zum Generieren von Dokumentation gekennzeichnet ist, wird vom Compiler eine ID-Zeichenfolge generiert.</span><span class="sxs-lookup"><span data-stu-id="1e64d-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="1e64d-104">(Informationen zum Kennzeichnen von Code finden Sie unter [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) Das Konstrukt wird über die ID-Zeichenfolge eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1e64d-104">(For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="1e64d-105">Programme, die die XML-Datei verarbeiten können die ID-Zeichenfolge zum Identifizieren der entsprechenden [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Metadaten/Reflektion-Element.</span><span class="sxs-lookup"><span data-stu-id="1e64d-105">Programs that process the XML file can use the ID string to identify the corresponding [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] metadata/reflection item.</span></span>  
  
 <span data-ttu-id="1e64d-106">Die XML-Datei ist nicht über eine hierarchische Darstellung des Codes; Es ist eine flache Liste mit einer generierten ID für jedes Element.</span><span class="sxs-lookup"><span data-stu-id="1e64d-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span></span>  
  
 <span data-ttu-id="1e64d-107">Der Compiler beachtet beim Generieren der ID-Zeichenfolgen die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="1e64d-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
-   <span data-ttu-id="1e64d-108">In der Zeichenfolge wird kein Leerzeichen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="1e64d-108">No white space is placed in the string.</span></span>  
  
-   <span data-ttu-id="1e64d-109">Der erste Teil der ID-Zeichenfolge identifiziert die Art des Elements identifiziert wird, mit einem einzelnen Zeichen, gefolgt von einem Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="1e64d-109">The first part of the ID string identifies the kind of member being identified, with a single character followed by a colon.</span></span> <span data-ttu-id="1e64d-110">Die folgenden Elementtypen werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="1e64d-110">The following member types are used.</span></span>  
  
|<span data-ttu-id="1e64d-111">Zeichen</span><span class="sxs-lookup"><span data-stu-id="1e64d-111">Character</span></span>|<span data-ttu-id="1e64d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e64d-112">Description</span></span>|  
|---|---|  
|<span data-ttu-id="1e64d-113">N</span><span class="sxs-lookup"><span data-stu-id="1e64d-113">N</span></span>|<span data-ttu-id="1e64d-114">namespace</span><span class="sxs-lookup"><span data-stu-id="1e64d-114">namespace</span></span><br /><br /> <span data-ttu-id="1e64d-115">Ein Namespace können keine Dokumentationskommentare hinzugefügt, Sie können jedoch CREF-Verweise, sofern diese unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="1e64d-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span></span>|  
|<span data-ttu-id="1e64d-116">T</span><span class="sxs-lookup"><span data-stu-id="1e64d-116">T</span></span>|<span data-ttu-id="1e64d-117">Typ: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span><span class="sxs-lookup"><span data-stu-id="1e64d-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span></span>|  
|<span data-ttu-id="1e64d-118">F</span><span class="sxs-lookup"><span data-stu-id="1e64d-118">F</span></span>|<span data-ttu-id="1e64d-119">Feld: `Dim`</span><span class="sxs-lookup"><span data-stu-id="1e64d-119">field: `Dim`</span></span>|  
|<span data-ttu-id="1e64d-120">P</span><span class="sxs-lookup"><span data-stu-id="1e64d-120">P</span></span>|<span data-ttu-id="1e64d-121">Eigenschaft: `Property` (einschließlich Standardeigenschaften)</span><span class="sxs-lookup"><span data-stu-id="1e64d-121">property: `Property` (including default properties)</span></span>|  
|<span data-ttu-id="1e64d-122">M</span><span class="sxs-lookup"><span data-stu-id="1e64d-122">M</span></span>|<span data-ttu-id="1e64d-123">Methode: `Sub`, `Function`, `Declare`, `Operator`</span><span class="sxs-lookup"><span data-stu-id="1e64d-123">method: `Sub`, `Function`, `Declare`, `Operator`</span></span>|  
|<span data-ttu-id="1e64d-124">E</span><span class="sxs-lookup"><span data-stu-id="1e64d-124">E</span></span>|<span data-ttu-id="1e64d-125">Ereignis: `Event`</span><span class="sxs-lookup"><span data-stu-id="1e64d-125">event: `Event`</span></span>|  
|<span data-ttu-id="1e64d-126">!</span><span class="sxs-lookup"><span data-stu-id="1e64d-126">!</span></span>|<span data-ttu-id="1e64d-127">Fehlerzeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1e64d-127">error string</span></span><br /><br /> <span data-ttu-id="1e64d-128">Der verbleibende Teil der Zeichenfolge enthält Fehlerinformationen.</span><span class="sxs-lookup"><span data-stu-id="1e64d-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="1e64d-129">Visual Basic-Compiler generiert Fehlerinformationen für Links, die nicht aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="1e64d-129">The Visual Basic compiler generates error information for links that cannot be resolved.</span></span>|  
  
-   <span data-ttu-id="1e64d-130">Der zweite Teil der `String` ist der vollqualifizierte Name des Elements, angefangen beim Stamm des Namespaces.</span><span class="sxs-lookup"><span data-stu-id="1e64d-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="1e64d-131">Der Name des Elements, dessen einschließenden Typs und den Namespace werden durch Punkte getrennt.</span><span class="sxs-lookup"><span data-stu-id="1e64d-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span></span> <span data-ttu-id="1e64d-132">Wenn der Name des Elements selbst Punkte enthält, werden sie ersetzt, durch das Nummernzeichen (#).</span><span class="sxs-lookup"><span data-stu-id="1e64d-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span></span> <span data-ttu-id="1e64d-133">Es wird vorausgesetzt, dass kein Element mit einem Nummernzeichen direkt im Namen aufweist.</span><span class="sxs-lookup"><span data-stu-id="1e64d-133">It is assumed that no item has a number sign directly in its name.</span></span> <span data-ttu-id="1e64d-134">Z. B. den vollqualifizierten Namen des der `String` Konstruktor wäre `System.String.#ctor`.</span><span class="sxs-lookup"><span data-stu-id="1e64d-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span></span>  
  
-   <span data-ttu-id="1e64d-135">Wenn es sich bei Eigenschaften und Methoden um Argumente der Methode handelt, folgt die in Klammern eingeschlossene Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="1e64d-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="1e64d-136">Wenn keine Argumente vorhanden sind, werden keine Klammern verwendet.</span><span class="sxs-lookup"><span data-stu-id="1e64d-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="1e64d-137">Die Argumente werden durch Kommas voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="1e64d-137">The arguments are separated by commas.</span></span> <span data-ttu-id="1e64d-138">Die Codierung des jedes Argument folgt direkt Codieren in eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Signatur.</span><span class="sxs-lookup"><span data-stu-id="1e64d-138">The encoding of each argument follows directly how it is encoded in a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] signature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e64d-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e64d-139">Example</span></span>  
 <span data-ttu-id="1e64d-140">Der folgende Code zeigt, wie die ID-Zeichenfolgen für eine Klasse und ihre Member generiert.</span><span class="sxs-lookup"><span data-stu-id="1e64d-140">The following code shows how the ID strings for a class and its members are generated.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1e64d-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e64d-141">See Also</span></span>  
 [<span data-ttu-id="1e64d-142">/doc</span><span class="sxs-lookup"><span data-stu-id="1e64d-142">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [<span data-ttu-id="1e64d-143">Gewusst wie: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="1e64d-143">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
