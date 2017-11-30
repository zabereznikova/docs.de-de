---
title: Reflektion (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b7b94e25d2ca9563cd50f454c94092f18e295863
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="reflection-visual-basic"></a><span data-ttu-id="946f5-102">Reflektion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="946f5-102">Reflection (Visual Basic)</span></span>
<span data-ttu-id="946f5-103">Reflektion bietet Objekte (vom Typ <xref:System.Type>), die Assemblys, Module und Typen beschreiben.</span><span class="sxs-lookup"><span data-stu-id="946f5-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="946f5-104">Mithilfe von Reflektion können Sie dynamisch eine Instanz eines Typs erzeugen, den Typ an ein vorhandenes Objekt binden und Typinformationen von vorhandenen Objekten abfragen. Ebenso wird erläutert wie die Methoden vorhandener Objekte aufgerufen und auf ihre Felder und Eigenschaften zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="946f5-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="946f5-105">Wenn Sie Attribute in Ihrem Code verwenden, können Sie mit Reflektion auf diese zugreifen.</span><span class="sxs-lookup"><span data-stu-id="946f5-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="946f5-106">Weitere Informationen finden Sie unter [Attribute](https://msdn.microsoft.com/library/5x6cd29c).</span><span class="sxs-lookup"><span data-stu-id="946f5-106">For more information, see [Attributes](https://msdn.microsoft.com/library/5x6cd29c).</span></span>  
  
 <span data-ttu-id="946f5-107">Hier sehen Sie ein einfaches Beispiel für Reflektion mit der statischen Methode `GetType`, die von allen Typen der Basisklasse `Object` geerbt wird, zum Abrufen von Typinformationen einer Variable:</span><span class="sxs-lookup"><span data-stu-id="946f5-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 <span data-ttu-id="946f5-108">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="946f5-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="946f5-109">Im folgenden Beispiel wird Reflektion verwendet, um den vollständigen Namen der geladenen Assembly abzurufen.</span><span class="sxs-lookup"><span data-stu-id="946f5-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 <span data-ttu-id="946f5-110">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="946f5-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a><span data-ttu-id="946f5-111">Übersicht über Reflektion</span><span class="sxs-lookup"><span data-stu-id="946f5-111">Reflection Overview</span></span>  
 <span data-ttu-id="946f5-112">Reflektion ist in folgenden Situationen nützlich:</span><span class="sxs-lookup"><span data-stu-id="946f5-112">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="946f5-113">Wenn Sie in den Metadaten Ihres Programms auf Attribute zugreifen müssen</span><span class="sxs-lookup"><span data-stu-id="946f5-113">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="946f5-114">Weitere Informationen finden Sie unter [Abrufen von Informationen aus Attributen](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="946f5-114">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
-   <span data-ttu-id="946f5-115">Zum Untersuchen und Instanziieren von Typen in einer Assembly</span><span class="sxs-lookup"><span data-stu-id="946f5-115">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="946f5-116">Zum Erstellen neuer Typen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="946f5-116">For building new types at runtime.</span></span> <span data-ttu-id="946f5-117">Verwenden Sie Klassen in <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="946f5-117">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="946f5-118">Zum Ausführen von spätem Binden mit Zugriff auf Methoden der zur Laufzeit erstellten Typen</span><span class="sxs-lookup"><span data-stu-id="946f5-118">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="946f5-119">Weitere Informationen finden Sie im Thema [Dynamisches Laden und Verwenden von Typen](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="946f5-119">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="946f5-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="946f5-120">Related Sections</span></span>  
 <span data-ttu-id="946f5-121">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="946f5-121">For more information:</span></span>  
  
-   [<span data-ttu-id="946f5-122">Reflektion</span><span class="sxs-lookup"><span data-stu-id="946f5-122">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [<span data-ttu-id="946f5-123">Anzeigen von Typinformationen</span><span class="sxs-lookup"><span data-stu-id="946f5-123">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [<span data-ttu-id="946f5-124">Reflektion und generische Typen</span><span class="sxs-lookup"><span data-stu-id="946f5-124">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [<span data-ttu-id="946f5-125">Abrufen von Informationen aus Attributen</span><span class="sxs-lookup"><span data-stu-id="946f5-125">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a><span data-ttu-id="946f5-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="946f5-126">See Also</span></span>  
 [<span data-ttu-id="946f5-127">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="946f5-127">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)  
 [<span data-ttu-id="946f5-128">Assemblys in der Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="946f5-128">Assemblies in the Common Language Runtime</span></span>](https://msdn.microsoft.com/library/k3677y81)
