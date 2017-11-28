---
title: Benutzerdefinierte Funktionen und Variablen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 4772f20e-1e7f-496e-93c2-1484473be555
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e1327ac2a3df7a84c157e4bf60d2ad63d69b1677
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="user-defined-functions-and-variables"></a><span data-ttu-id="2c15c-102">Benutzerdefinierte Funktionen und Variablen</span><span class="sxs-lookup"><span data-stu-id="2c15c-102">User Defined Functions and Variables</span></span>
<span data-ttu-id="2c15c-103">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt eine Gruppe von Methoden bereit, die zur Interaktion mit <xref:System.Xml.XPath.XPathDocument>-Daten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c15c-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods that are used to interact with <xref:System.Xml.XPath.XPathDocument> data.</span></span> <span data-ttu-id="2c15c-104">Sie können die standardmäßigen XPath-Funktionen durch Implementieren von Erweiterungsfunktionen und -variablen für XPath-Abfrageausdrücke ersetzen.</span><span class="sxs-lookup"><span data-stu-id="2c15c-104">You can supplement the standard XPath functions by implementing extension functions and variables for use by XPath query expressions.</span></span> <span data-ttu-id="2c15c-105">Die <xref:System.Xml.XPath.XPathExpression.SetContext%2A>-Methode akzeptiert einen von <xref:System.Xml.Xsl.XsltContext> abgeleiteten benutzerdefinierten Kontext.</span><span class="sxs-lookup"><span data-stu-id="2c15c-105">The <xref:System.Xml.XPath.XPathExpression.SetContext%2A> method can accept a user defined context derived from <xref:System.Xml.Xsl.XsltContext>.</span></span> <span data-ttu-id="2c15c-106">Benutzerdefinierte Funktionen werden von dem benutzerdefinierten Kontext aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="2c15c-106">User defined functions are resolved by the custom context.</span></span>  
  
 <span data-ttu-id="2c15c-107">Erweiterungsfunktionen und -variablen können nützlich zum Vermeiden von XML-Injection-Angriffen sein.</span><span class="sxs-lookup"><span data-stu-id="2c15c-107">Extension functions and variables can be useful in prevention of XML injection attacks.</span></span> <span data-ttu-id="2c15c-108">In diesen Szenarios werden Benutzereingaben benutzerdefinierten Variablen zugewiesen und mittels Erweiterungsfunktionen verarbeitet und nicht einfach mit Verarbeitungsanweisungen verkettet.</span><span class="sxs-lookup"><span data-stu-id="2c15c-108">In these scenarios user input is assigned to custom variables and processed by extension functions, not as raw input concatenated with processing instructions.</span></span> <span data-ttu-id="2c15c-109">Erweiterungsfunktionen und -variablen enthalten Benutzereingaben, sodass nur die vom Designer vorgesehenen Aktionen für XML-Daten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2c15c-109">Extension functions and variables contain user input so that it only acts on XML data as intended by the designer.</span></span>  
  
 <span data-ttu-id="2c15c-110">Zum Verwenden von Erweiterungen implementieren Sie eine benutzerdefinierte <xref:System.Xml.Xsl.XsltContext>-Klasse mit den Schnittstellen <xref:System.Xml.Xsl.IXsltContextFunction> und <xref:System.Xml.Xsl.IXsltContextVariable>, die Erweiterungsfunktionen und -variablen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2c15c-110">To use extensions you implement a custom <xref:System.Xml.Xsl.XsltContext> class along with the interfaces <xref:System.Xml.Xsl.IXsltContextFunction> and <xref:System.Xml.Xsl.IXsltContextVariable> that support extension functions and variables.</span></span> <span data-ttu-id="2c15c-111">Ein <xref:System.Xml.XPath.XPathExpression> fügt Benutzereingaben mithilfe des zugehörigen <xref:System.Xml.Xsl.XsltArgumentList>-Elements dem benutzerdefinierten <xref:System.Xml.Xsl.XsltContext> hinzu.</span><span class="sxs-lookup"><span data-stu-id="2c15c-111">An <xref:System.Xml.XPath.XPathExpression> adds user input with its <xref:System.Xml.Xsl.XsltArgumentList> to the custom <xref:System.Xml.Xsl.XsltContext>.</span></span>  
  
 <span data-ttu-id="2c15c-112">Der <xref:System.Xml.XPath.XPathExpression> stellt eine kompilierte Abfrage dar, die vom <xref:System.Xml.XPath.XPathNavigator> verwendet wird, um die im Ausdruck bezeichneten Knoten zu suchen und zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2c15c-112">The <xref:System.Xml.XPath.XPathExpression> represents a compiled query that <xref:System.Xml.XPath.XPathNavigator> uses to find and process the nodes identified by the expression.</span></span>  
  
 <span data-ttu-id="2c15c-113">Das folgende Beispiel zeigt die Implementierung einer benutzerdefinierten Kontextklasse, die von <xref:System.Xml.Xsl.XsltContext> abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="2c15c-113">The following example shows implementation of a custom context class derived from <xref:System.Xml.Xsl.XsltContext>.</span></span> <span data-ttu-id="2c15c-114">In den Kommentaren im Code werden Klassenmember und deren Verwendung in benutzerdefinierten Funktionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2c15c-114">Comments in the code describe class members and their use in custom functions.</span></span> <span data-ttu-id="2c15c-115">Auf dieses Codesegment folgen Implementierungen von Funktionen und Variablen und eine Beispielanwendung, die diese Implementierungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2c15c-115">Function and variable implementations and a sample application that uses these implementations follow this code segment.</span></span>  
  
 [!code-csharp[XPathExtensionFunctions#2](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#2)]
 [!code-vb[XPathExtensionFunctions#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#2)]  
  
 <span data-ttu-id="2c15c-116">Mit dem folgenden Code wird das <xref:System.Xml.Xsl.IXsltContextFunction>-Element implementiert.</span><span class="sxs-lookup"><span data-stu-id="2c15c-116">The following code implements <xref:System.Xml.Xsl.IXsltContextFunction>.</span></span> <span data-ttu-id="2c15c-117">Die Klasse, die das <xref:System.Xml.Xsl.IXsltContextFunction>-Element implementiert, löst benutzerdefinierte Funktionen auf und führt sie aus.</span><span class="sxs-lookup"><span data-stu-id="2c15c-117">The class that implements <xref:System.Xml.Xsl.IXsltContextFunction> resolves and executes user-defined functions.</span></span> <span data-ttu-id="2c15c-118">In diesem Beispiel wird die mit der folgenden Deklaration identifizierte Funktion verwendet: `private int CountChar(string title, char charTocount)`.</span><span class="sxs-lookup"><span data-stu-id="2c15c-118">This example uses the function identified by the declaration: `private int CountChar(string title, char charTocount)`.</span></span>  
  
 <span data-ttu-id="2c15c-119">Mit den Kommentaren im Code werden Klassenmember beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2c15c-119">Code comments describe class members.</span></span>  
  
 [!code-csharp[XPathExtensionFunctions#3](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#3)]
 [!code-vb[XPathExtensionFunctions#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#3)]  
  
 <span data-ttu-id="2c15c-120">Mit dem folgenden Code wird das <xref:System.Xml.Xsl.IXsltContextVariable>-Element implementiert.</span><span class="sxs-lookup"><span data-stu-id="2c15c-120">The following code implements <xref:System.Xml.Xsl.IXsltContextVariable>.</span></span> <span data-ttu-id="2c15c-121">Diese Klasse löst Verweise auf benutzerdefinierte Variablen in XPath-Abfrageausdrücken zur Laufzeit auf.</span><span class="sxs-lookup"><span data-stu-id="2c15c-121">This class resolves references to user-defined variables in XPath query expressions at run time.</span></span> <span data-ttu-id="2c15c-122">Eine Instanz dieser Klasse wird erstellt und von der überschriebenen <xref:System.Xml.Xsl.XsltContext.ResolveVariable%2A>-Methode der benutzerdefinierten <xref:System.Xml.Xsl.XsltContext>-Klasse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2c15c-122">An instance of this class is created and returned by the overridden <xref:System.Xml.Xsl.XsltContext.ResolveVariable%2A> method of the custom <xref:System.Xml.Xsl.XsltContext> class.</span></span>  
  
 <span data-ttu-id="2c15c-123">Mit den Kommentaren im Code werden die Klassenmember beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2c15c-123">Code comments describe the class members.</span></span>  
  
 [!code-csharp[XPathExtensionFunctions#4](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#4)]
 [!code-vb[XPathExtensionFunctions#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#4)]  
  
 <span data-ttu-id="2c15c-124">Im folgenden Code wird die benutzerdefinierte Funktion verwendet, um die Zeichen in den Elementen des `Tasks.xml`-Dokuments zu zählen (mit den vorherigen gültigen Klassendefinitionen).</span><span class="sxs-lookup"><span data-stu-id="2c15c-124">With the previous class definitions in scope, the following code uses the custom function to count characters in the elements of the `Tasks.xml` document.</span></span> <span data-ttu-id="2c15c-125">Mit den Kommentaren im Code wird der Code beschrieben, der die benutzerdefinierte Funktion kompiliert und auf das `Tasks.xml`-Dokument anwendet.</span><span class="sxs-lookup"><span data-stu-id="2c15c-125">Comments in the code describe the code that compiles the custom function and runs it against the `Tasks.xml` document.</span></span>  
  
 [!code-csharp[XPathExtensionFunctions#1](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#1)]
 [!code-vb[XPathExtensionFunctions#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#1)]  
  
 <span data-ttu-id="2c15c-126">In diesem Beispiel werden die folgenden XML-Daten verwendet.</span><span class="sxs-lookup"><span data-stu-id="2c15c-126">This example uses the following XML data.</span></span>  
  
 [!code-xml[XPathExtensionFunctions#5](../../../../samples/snippets/xml/VS_Snippets_Data/xpathextensionfunctions/XML/tasks.xml#5)]
