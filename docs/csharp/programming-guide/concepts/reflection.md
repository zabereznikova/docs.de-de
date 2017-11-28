---
title: Reflektion (C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f567eb47d93fcd95e5895b4b44e1c89fb0b901b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="reflection-c"></a><span data-ttu-id="6880b-102">Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="6880b-102">Reflection (C#)</span></span>
<span data-ttu-id="6880b-103">Reflektion bietet Objekte (vom Typ <xref:System.Type>), die Assemblys, Module und Typen beschreiben.</span><span class="sxs-lookup"><span data-stu-id="6880b-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="6880b-104">Mithilfe von Reflektion können Sie dynamisch eine Instanz eines Typs erzeugen, den Typ an ein vorhandenes Objekt binden und Typinformationen von vorhandenen Objekten abfragen. Ebenso wird erläutert wie die Methoden vorhandener Objekte aufgerufen und auf ihre Felder und Eigenschaften zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="6880b-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="6880b-105">Wenn Sie Attribute in Ihrem Code verwenden, können Sie mit Reflektion auf diese zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6880b-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="6880b-106">Weitere Informationen finden Sie unter [Attribute](https://msdn.microsoft.com/library/5x6cd29c).</span><span class="sxs-lookup"><span data-stu-id="6880b-106">For more information, see [Attributes](https://msdn.microsoft.com/library/5x6cd29c).</span></span>  
  
 <span data-ttu-id="6880b-107">Hier sehen Sie ein einfaches Beispiel für Reflektion mit der statischen Methode `GetType`, die von allen Typen der Basisklasse `Object` geerbt wird, zum Abrufen von Typinformationen einer Variable:</span><span class="sxs-lookup"><span data-stu-id="6880b-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```csharp  
// Using GetType to obtain type information:  
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type);  
```  
  
 <span data-ttu-id="6880b-108">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6880b-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="6880b-109">Im folgenden Beispiel wird Reflektion verwendet, um den vollständigen Namen der geladenen Assembly abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6880b-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```csharp  
// Using Reflection to get information from an Assembly:  
System.Reflection.Assembly info = typeof(System.Int32).Assembly;  
System.Console.WriteLine(info);  
```  
  
 <span data-ttu-id="6880b-110">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6880b-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
> [!NOTE]
>  <span data-ttu-id="6880b-111">Die C#-Schlüsselwörter `protected` und `internal` haben in IL keine Bedeutung und werden nicht in Reflektions-APIs verwendet.</span><span class="sxs-lookup"><span data-stu-id="6880b-111">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="6880b-112">Die entsprechenden Begriffe in IL sind *Family* und *Assembly*.</span><span class="sxs-lookup"><span data-stu-id="6880b-112">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="6880b-113">Verwenden Sie zum Identifizieren einer `internal`-Methode mithilfe von Reflektion die Eigenschaft <xref:System.Reflection.MethodBase.IsAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="6880b-113">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="6880b-114">Verwenden Sie <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A> zum Identifizieren einer Methode `protected internal`.</span><span class="sxs-lookup"><span data-stu-id="6880b-114">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>  
  
## <a name="reflection-overview"></a><span data-ttu-id="6880b-115">Übersicht über Reflektion</span><span class="sxs-lookup"><span data-stu-id="6880b-115">Reflection Overview</span></span>  
 <span data-ttu-id="6880b-116">Reflektion ist in folgenden Situationen nützlich:</span><span class="sxs-lookup"><span data-stu-id="6880b-116">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="6880b-117">Wenn Sie in den Metadaten Ihres Programms auf Attribute zugreifen müssen</span><span class="sxs-lookup"><span data-stu-id="6880b-117">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="6880b-118">Weitere Informationen finden Sie unter [Abrufen von Informationen aus Attributen](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="6880b-118">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
-   <span data-ttu-id="6880b-119">Zum Untersuchen und Instanziieren von Typen in einer Assembly</span><span class="sxs-lookup"><span data-stu-id="6880b-119">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="6880b-120">Zum Erstellen neuer Typen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="6880b-120">For building new types at runtime.</span></span> <span data-ttu-id="6880b-121">Verwenden Sie Klassen in <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="6880b-121">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="6880b-122">Zum Ausführen von spätem Binden mit Zugriff auf Methoden der zur Laufzeit erstellten Typen</span><span class="sxs-lookup"><span data-stu-id="6880b-122">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="6880b-123">Weitere Informationen finden Sie im Thema [Dynamisches Laden und Verwenden von Typen](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="6880b-123">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6880b-124">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="6880b-124">Related Sections</span></span>  
 <span data-ttu-id="6880b-125">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="6880b-125">For more information:</span></span>  
  
-   [<span data-ttu-id="6880b-126">Reflektion</span><span class="sxs-lookup"><span data-stu-id="6880b-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [<span data-ttu-id="6880b-127">Anzeigen von Typinformationen</span><span class="sxs-lookup"><span data-stu-id="6880b-127">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [<span data-ttu-id="6880b-128">Reflektion und generische Typen</span><span class="sxs-lookup"><span data-stu-id="6880b-128">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [<span data-ttu-id="6880b-129">Abrufen von Informationen aus Attributen</span><span class="sxs-lookup"><span data-stu-id="6880b-129">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a><span data-ttu-id="6880b-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6880b-130">See Also</span></span>  
 [<span data-ttu-id="6880b-131">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6880b-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6880b-132">Assemblys in der Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="6880b-132">Assemblies in the Common Language Runtime</span></span>](https://msdn.microsoft.com/library/k3677y81)
