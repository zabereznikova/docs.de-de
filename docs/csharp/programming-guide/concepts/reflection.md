---
title: Reflektion (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: 4dfd9391407fec4bd20ac4ae05162763e909d665
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841315"
---
# <a name="reflection-c"></a><span data-ttu-id="1631c-102">Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="1631c-102">Reflection (C#)</span></span>
<span data-ttu-id="1631c-103">Reflektion bietet Objekte (vom Typ <xref:System.Type>), die Assemblys, Module und Typen beschreiben.</span><span class="sxs-lookup"><span data-stu-id="1631c-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="1631c-104">Mithilfe von Reflektion können Sie dynamisch eine Instanz eines Typs erzeugen, den Typ an ein vorhandenes Objekt binden und Typinformationen von vorhandenen Objekten abfragen. Ebenso wird erläutert wie die Methoden vorhandener Objekte aufgerufen und auf ihre Felder und Eigenschaften zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1631c-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="1631c-105">Wenn Sie Attribute in Ihrem Code verwenden, können Sie mit Reflektion auf diese zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1631c-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="1631c-106">Weitere Informationen finden Sie unter [Attribute](../../../../docs/standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="1631c-106">For more information, see [Attributes](../../../../docs/standard/attributes/index.md).</span></span>  
  
 <span data-ttu-id="1631c-107">Hier sehen Sie ein einfaches Beispiel für Reflektion mit der statischen Methode `GetType`, die von allen Typen der Basisklasse `Object` geerbt wird, zum Abrufen von Typinformationen einer Variable:</span><span class="sxs-lookup"><span data-stu-id="1631c-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```csharp  
// Using GetType to obtain type information:  
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type);  
```  
  
 <span data-ttu-id="1631c-108">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1631c-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="1631c-109">Im folgenden Beispiel wird Reflektion verwendet, um den vollständigen Namen der geladenen Assembly abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1631c-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```csharp  
// Using Reflection to get information of an Assembly:  
System.Reflection.Assembly info = typeof(System.Int32).Assembly;  
System.Console.WriteLine(info);  
```  
  
 <span data-ttu-id="1631c-110">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1631c-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
> [!NOTE]
>  <span data-ttu-id="1631c-111">Die C#-Schlüsselwörter `protected` und `internal` haben in IL keine Bedeutung und werden nicht in Reflektions-APIs verwendet.</span><span class="sxs-lookup"><span data-stu-id="1631c-111">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="1631c-112">Die entsprechenden Begriffe in IL sind *Family* und *Assembly*.</span><span class="sxs-lookup"><span data-stu-id="1631c-112">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="1631c-113">Verwenden Sie zum Identifizieren einer `internal`-Methode mithilfe von Reflektion die Eigenschaft <xref:System.Reflection.MethodBase.IsAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="1631c-113">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="1631c-114">Verwenden Sie <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A> zum Identifizieren einer Methode `protected internal`.</span><span class="sxs-lookup"><span data-stu-id="1631c-114">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>  
  
## <a name="reflection-overview"></a><span data-ttu-id="1631c-115">Übersicht über Reflektion</span><span class="sxs-lookup"><span data-stu-id="1631c-115">Reflection Overview</span></span>  
 <span data-ttu-id="1631c-116">Reflektion ist in folgenden Situationen nützlich:</span><span class="sxs-lookup"><span data-stu-id="1631c-116">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="1631c-117">Wenn Sie in den Metadaten Ihres Programms auf Attribute zugreifen müssen</span><span class="sxs-lookup"><span data-stu-id="1631c-117">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="1631c-118">Weitere Informationen finden Sie unter [Abrufen von Informationen aus Attributen](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="1631c-118">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>  
  
-   <span data-ttu-id="1631c-119">Zum Untersuchen und Instanziieren von Typen in einer Assembly</span><span class="sxs-lookup"><span data-stu-id="1631c-119">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="1631c-120">Zum Erstellen neuer Typen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1631c-120">For building new types at runtime.</span></span> <span data-ttu-id="1631c-121">Verwenden Sie Klassen in <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="1631c-121">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="1631c-122">Zum Ausführen von spätem Binden mit Zugriff auf Methoden der zur Laufzeit erstellten Typen</span><span class="sxs-lookup"><span data-stu-id="1631c-122">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="1631c-123">Weitere Informationen finden Sie im Thema [Dynamisches Laden und Verwenden von Typen](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="1631c-123">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1631c-124">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1631c-124">Related Sections</span></span>  
 <span data-ttu-id="1631c-125">Weitere Informationen finden Sie unter: </span><span class="sxs-lookup"><span data-stu-id="1631c-125">For more information:</span></span>  
  
-   [<span data-ttu-id="1631c-126">Reflexion</span><span class="sxs-lookup"><span data-stu-id="1631c-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
  
-   [<span data-ttu-id="1631c-127">Anzeigen von Typinformationen</span><span class="sxs-lookup"><span data-stu-id="1631c-127">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)  
  
-   [<span data-ttu-id="1631c-128">Reflektion und generische Typen</span><span class="sxs-lookup"><span data-stu-id="1631c-128">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)  
  
-   <xref:System.Reflection.Emit>  
  
-   [<span data-ttu-id="1631c-129">Abrufen von Informationen aus Attributen</span><span class="sxs-lookup"><span data-stu-id="1631c-129">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
  
## <a name="see-also"></a><span data-ttu-id="1631c-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1631c-130">See also</span></span>

- [<span data-ttu-id="1631c-131">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1631c-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1631c-132">Assemblys in der Common Language Runtime (CLR)</span><span class="sxs-lookup"><span data-stu-id="1631c-132">Assemblies in the Common Language Runtime</span></span>](../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
