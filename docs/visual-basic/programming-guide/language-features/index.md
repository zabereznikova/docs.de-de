---
title: "Funktionen von Visual Basic"
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
- Visual Basic code, elements of
- Visual Basic code
ms.assetid: b0b21730-298c-47e6-9a2f-cc81f628067b
caps.latest.revision: 18
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3594e6622e8bc76839a15739a31ad27d17de8455
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="visual-basic-language-features"></a><span data-ttu-id="ac616-102">Funktionen von Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac616-102">Visual Basic Language Features</span></span>
<span data-ttu-id="ac616-103">In den folgenden Themen werden die wesentlichen Komponenten von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], einer objektorientierten Programmiersprache, vorgestellt und erläutert.</span><span class="sxs-lookup"><span data-stu-id="ac616-103">The following topics introduce and discuss the essential components of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], an object-oriented programming language.</span></span> <span data-ttu-id="ac616-104">Nachdem Sie mithilfe von Formularen und Steuerelementen die Benutzerschnittstelle für Ihre Anwendung erstellt haben, müssen Sie den Code schreiben, der das Verhalten der Anwendung definiert.</span><span class="sxs-lookup"><span data-stu-id="ac616-104">After creating the user interface for your application using forms and controls, you need to write the code that defines the application's behavior.</span></span> <span data-ttu-id="ac616-105">Wie jede moderne Programmiersprache unterstützt auch [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] eine Reihe allgemeiner Programmierungskonstrukte und Sprachelemente.</span><span class="sxs-lookup"><span data-stu-id="ac616-105">As with any modern programming language, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] supports a number of common programming constructs and language elements.</span></span>  
  
 <span data-ttu-id="ac616-106">Wenn Sie bereits in anderen Sprachen programmiert haben, wird Ihnen vieles in diesem Abschnitt bekannt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ac616-106">If you have programmed in other languages, much of the material covered in this section might seem familiar.</span></span> <span data-ttu-id="ac616-107">Die meisten Konstrukte ähneln denen in anderen Sprachen. Allerdings gibt es aufgrund der ereignisgesteuerten Natur von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] einige feine Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="ac616-107">While most of the constructs are similar to those in other languages, the event-driven nature of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] introduces some subtle differences.</span></span>  
  
 <span data-ttu-id="ac616-108">Wenn Sie noch keine Erfahrung mit dem Programmieren haben, erhalten Sie in diesem Abschnitt eine Einführung in die grundlegenden Bausteine für das Schreiben von Code.</span><span class="sxs-lookup"><span data-stu-id="ac616-108">If you are new to programming, the material in this section serves as an introduction to the basic building blocks for writing code.</span></span> <span data-ttu-id="ac616-109">Sobald Sie mit den Grundlagen vertraut sind, können Sie mit [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] leistungsstarke Anwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="ac616-109">Once you understand the basics, you can create powerful applications using [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac616-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ac616-110">In This Section</span></span>  
 [<span data-ttu-id="ac616-111">Arrays</span><span class="sxs-lookup"><span data-stu-id="ac616-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 <span data-ttu-id="ac616-112">Dieser Artikel erläutert, wie Sie Ihren Code kompakter und leistungsfähiger machen, indem Sie Arrays deklarieren und verwenden, die mehrere zusammengehörige Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="ac616-112">Discusses making your code more compact and powerful by declaring and using arrays, which hold multiple related values.</span></span>  
  
 [<span data-ttu-id="ac616-113">Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="ac616-113">Collection Initializers</span></span>](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 <span data-ttu-id="ac616-114">Dieser Artikel beschreibt Auflistungsinitialisierer, mit denen Sie eine Auflistung erstellen und mit einem anfänglichen Satz von Werten auffüllen können.</span><span class="sxs-lookup"><span data-stu-id="ac616-114">Describes collection initializers, which enable you to create a collection and populate it with an initial set of values.</span></span>  
  
 [<span data-ttu-id="ac616-115">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ac616-115">Constants and Enumerations</span></span>](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 <span data-ttu-id="ac616-116">Dieser Artikel erläutert die Speicherung unveränderter Werte für die wiederholte Verwendung, einschließlich eines Satzes zusammengehöriger konstanter Werte.</span><span class="sxs-lookup"><span data-stu-id="ac616-116">Discusses storing unchanging values for repeated use, including sets of related constant values.</span></span>  
  
 [<span data-ttu-id="ac616-117">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="ac616-117">Control Flow</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 <span data-ttu-id="ac616-118">Dieser Artikel zeigt Ihnen, wie Sie den Ablauf der Ausführung Ihres Programms steuern.</span><span class="sxs-lookup"><span data-stu-id="ac616-118">Shows how to regulate the flow of your program's execution.</span></span>  
  
 [<span data-ttu-id="ac616-119">Datentypen</span><span class="sxs-lookup"><span data-stu-id="ac616-119">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="ac616-120">Dieser Artikel beschreibt, welche Arten von Daten ein Programmierelement enthalten kann und wie diese Daten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ac616-120">Describes what kinds of data a programming element can hold and how that data is stored.</span></span>  
  
 [<span data-ttu-id="ac616-121">Deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="ac616-121">Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 <span data-ttu-id="ac616-122">Dieser Artikel beschreibt Programmierelemente, die Sie deklarieren können, ihre Namen und Merkmale, und erläutert, wie der Compiler Verweise auf diese Elemente auflöst.</span><span class="sxs-lookup"><span data-stu-id="ac616-122">Covers programming elements you can declare, their names and characteristics, and how the compiler resolves references to them.</span></span>  
  
 [<span data-ttu-id="ac616-123">Delegaten</span><span class="sxs-lookup"><span data-stu-id="ac616-123">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 <span data-ttu-id="ac616-124">Dieser Artikel stellt Delegaten vor und erläutert, wie sie in Visual Basic verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac616-124">Provides an introduction to delegates and how they are used in Visual Basic.</span></span>  
  
 [<span data-ttu-id="ac616-125">Frühes und spätes Binden</span><span class="sxs-lookup"><span data-stu-id="ac616-125">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 <span data-ttu-id="ac616-126">Dieser Artikel beschreibt die Bindung, die vom Compiler ausgeführt wird, wenn ein Objekt einer Objektvariablen zugewiesen wird, sowie die Unterschiede zwischen früh gebundenen und spät gebundenen Objekten.</span><span class="sxs-lookup"><span data-stu-id="ac616-126">Describes binding, which is performed by the compiler when an object is assigned to an object variable, and the differences between early-bound and late-bound objects.</span></span>  
  
 [<span data-ttu-id="ac616-127">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="ac616-127">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 <span data-ttu-id="ac616-128">Dieser Artikel bietet eine Übersicht über Syntaxfehler, Laufzeitfehler und Logikfehler.</span><span class="sxs-lookup"><span data-stu-id="ac616-128">Provides an overview of syntax errors, run-time errors, and logic errors.</span></span>  
  
 [<span data-ttu-id="ac616-129">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="ac616-129">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)  
 <span data-ttu-id="ac616-130">Dieser Artikel zeigt, wie Sie Ereignisse deklarieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac616-130">Shows how to declare and use events.</span></span>  
  
 [<span data-ttu-id="ac616-131">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ac616-131">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 <span data-ttu-id="ac616-132">Dieser Artikel beschreibt, was Schnittstellen sind und wie Sie diese in Ihren Anwendungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ac616-132">Describes what interfaces are and how you can use them in your applications.</span></span>  
  
 [<span data-ttu-id="ac616-133">LINQ</span><span class="sxs-lookup"><span data-stu-id="ac616-133">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="ac616-134">Dieser Artikel stellt Links zu Themen bereit, die Features und Programmierelemente von [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] einführen.</span><span class="sxs-lookup"><span data-stu-id="ac616-134">Provides links to topics that introduce [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] features and programming.</span></span>  
  
 [<span data-ttu-id="ac616-135">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="ac616-135">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 <span data-ttu-id="ac616-136">Dieser Artikel bietet eine Übersicht über Objekte und Klassen, ihre Verwendung, ihre Beziehungen zueinander sowie die Eigenschaften, Methoden und Ereignisse, die sie verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="ac616-136">Provides an overview of objects and classes, how they are used, their relationships to each other, and the properties, methods, and events they expose.</span></span>  
  
 [<span data-ttu-id="ac616-137">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ac616-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 <span data-ttu-id="ac616-138">Dieser Artikel beschreibt die Codeelemente, die Elemente mit Werten ändern. Es wird auch erläutert, wie Sie diese Codeelemente effizient verwenden und zum Erzielen neuer Werte kombinieren.</span><span class="sxs-lookup"><span data-stu-id="ac616-138">Describes the code elements that manipulate value-holding elements, how to use them efficiently, and how to combine them to yield new values.</span></span>  
  
 [<span data-ttu-id="ac616-139">Verfahren</span><span class="sxs-lookup"><span data-stu-id="ac616-139">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 <span data-ttu-id="ac616-140">Dieser Artikel beschreibt die Prozeduren `Sub`, `Function`, `Property` und `Operator` und bietet Informationen zu weiterführenden Themen wie rekursiven und überladenen Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="ac616-140">Describes `Sub`, `Function`, `Property`, and `Operator` procedures, as well as advanced topics such as recursive and overloaded procedures.</span></span>  
  
 [<span data-ttu-id="ac616-141">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="ac616-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 <span data-ttu-id="ac616-142">Dieser Artikel beschreibt Deklarationen und ausführbare Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="ac616-142">Describes declaration and executable statements.</span></span>  
  
 [<span data-ttu-id="ac616-143">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ac616-143">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 <span data-ttu-id="ac616-144">Dieser Artikel enthält Links zu Themen, die grundlegende Konzepte zur Verwendung von Zeichenfolgen in Visual Basic beschreiben.</span><span class="sxs-lookup"><span data-stu-id="ac616-144">Provides links to topics that describe the basic concepts about using strings in Visual Basic.</span></span>  
  
 [<span data-ttu-id="ac616-145">Variablen</span><span class="sxs-lookup"><span data-stu-id="ac616-145">Variables</span></span>](../../../visual-basic/programming-guide/language-features/variables/index.md)  
 <span data-ttu-id="ac616-146">Dieser Artikel stellt Variablen vor und beschreibt deren Verwendung in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ac616-146">Introduces variables and describes how to use them in Visual Basic.</span></span>  
  
 [<span data-ttu-id="ac616-147">XML</span><span class="sxs-lookup"><span data-stu-id="ac616-147">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="ac616-148">Dieser Artikel enthält Links zu Themen, in denen die Verwendung von XML in Visual Basic beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="ac616-148">Provides links to topics that describe how to use XML in Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ac616-149">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ac616-149">Related Sections</span></span>  
 [<span data-ttu-id="ac616-150">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="ac616-150">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
 <span data-ttu-id="ac616-151">Dieser Artikel beschreibt einige der Auflistungstypen, die von .NET Framework bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ac616-151">Describes some of the types of collections that are provided by the .NET Framework.</span></span> <span data-ttu-id="ac616-152">Veranschaulicht, wie einfache Auflistungen und Auflistungen von Schlüssel-Wert-Paaren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac616-152">Demonstrates how to use simple collections and collections of key/value pairs.</span></span>  
  
 [<span data-ttu-id="ac616-153">Sprachreferenz zu Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac616-153">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
 <span data-ttu-id="ac616-154">Dieser Artikel enthält Referenzinformationen zu verschiedenen Aspekten der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="ac616-154">Provides reference information on various aspects of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programming.</span></span>

