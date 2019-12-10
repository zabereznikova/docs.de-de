---
title: Reflektion (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: a56fb24b63e4d80dbb67b079466b67cd11672023
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711658"
---
# <a name="reflection-c"></a><span data-ttu-id="d6966-102">Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="d6966-102">Reflection (C#)</span></span>

<span data-ttu-id="d6966-103">Reflektion bietet Objekte (des Typs <xref:System.Type>), die Assemblys, Module und Typen beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d6966-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules, and types.</span></span> <span data-ttu-id="d6966-104">Mithilfe von Reflektion können Sie dynamisch eine Instanz eines Typs erzeugen, den Typ an ein vorhandenes Objekt binden und Typinformationen von vorhandenen Objekten abfragen. Ebenso wird erläutert wie die Methoden vorhandener Objekte aufgerufen und auf ihre Felder und Eigenschaften zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d6966-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="d6966-105">Wenn Sie Attribute in Ihrem Code verwenden, können Sie mit Reflektion auf diese zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d6966-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="d6966-106">Weitere Informationen finden Sie unter [Attribute](../../../standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="d6966-106">For more information, see [Attributes](../../../standard/attributes/index.md).</span></span>

<span data-ttu-id="d6966-107">Hier sehen Sie ein einfaches Beispiel für Reflektion mit der Methode <xref:System.Object.GetType>, die von allen Typen der Basisklasse `Object` geerbt wird, zum Abrufen von Typinformationen einer Variable:</span><span class="sxs-lookup"><span data-stu-id="d6966-107">Here's a simple example of reflection using the <xref:System.Object.GetType> method - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>

> [!NOTE]
> <span data-ttu-id="d6966-108">Stellen Sie sicher, dass Sie `using System;` und `using System.Reflection;` am Anfang Ihrer *.cs*-Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6966-108">Make sure you add `using System;` and `using System.Reflection;` at the top of your *.cs* file.</span></span>

```csharp
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type);
```

<span data-ttu-id="d6966-109">Die Ausgabe ist: `System.Int32`.</span><span class="sxs-lookup"><span data-stu-id="d6966-109">The output is: `System.Int32`.</span></span>

<span data-ttu-id="d6966-110">Im folgenden Beispiel wird Reflektion verwendet, um den vollständigen Namen der geladenen Assembly abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d6966-110">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>

```csharp
// Using Reflection to get information of an Assembly:
Assembly info = typeof(int).Assembly;
Console.WriteLine(info);
```

<span data-ttu-id="d6966-111">Die Ausgabe ist: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span><span class="sxs-lookup"><span data-stu-id="d6966-111">The output is: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span></span>

> [!NOTE]
> <span data-ttu-id="d6966-112">Die C#-Schlüsselwörter `protected` und `internal` haben in IL keine Bedeutung und werden nicht in Reflektions-APIs verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6966-112">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="d6966-113">Die entsprechenden Begriffe in IL sind *Family* und *Assembly*.</span><span class="sxs-lookup"><span data-stu-id="d6966-113">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="d6966-114">Verwenden Sie zum Identifizieren einer `internal`-Methode mithilfe von Reflektion die Eigenschaft <xref:System.Reflection.MethodBase.IsAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="d6966-114">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="d6966-115">Verwenden Sie <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A> zum Identifizieren einer Methode `protected internal`.</span><span class="sxs-lookup"><span data-stu-id="d6966-115">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>

## <a name="reflection-overview"></a><span data-ttu-id="d6966-116">Übersicht über Reflektion</span><span class="sxs-lookup"><span data-stu-id="d6966-116">Reflection overview</span></span>

<span data-ttu-id="d6966-117">Reflektion ist in folgenden Situationen nützlich:</span><span class="sxs-lookup"><span data-stu-id="d6966-117">Reflection is useful in the following situations:</span></span>

- <span data-ttu-id="d6966-118">Wenn Sie in den Metadaten Ihres Programms auf Attribute zugreifen müssen</span><span class="sxs-lookup"><span data-stu-id="d6966-118">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="d6966-119">Weitere Informationen finden Sie unter [Abrufen von Informationen aus Attributen](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="d6966-119">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>
- <span data-ttu-id="d6966-120">Zum Untersuchen und Instanziieren von Typen in einer Assembly</span><span class="sxs-lookup"><span data-stu-id="d6966-120">For examining and instantiating types in an assembly.</span></span>
- <span data-ttu-id="d6966-121">Zum Erstellen neuer Typen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d6966-121">For building new types at runtime.</span></span> <span data-ttu-id="d6966-122">Verwenden Sie Klassen in <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="d6966-122">Use classes in <xref:System.Reflection.Emit>.</span></span>
- <span data-ttu-id="d6966-123">Zum Ausführen von spätem Binden mit Zugriff auf Methoden der zur Laufzeit erstellten Typen</span><span class="sxs-lookup"><span data-stu-id="d6966-123">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="d6966-124">Weitere Informationen finden Sie im Thema [Dynamisches Laden und Verwenden von Typen](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="d6966-124">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>

## <a name="related-sections"></a><span data-ttu-id="d6966-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d6966-125">Related sections</span></span>

<span data-ttu-id="d6966-126">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="d6966-126">For more information:</span></span>

- [<span data-ttu-id="d6966-127">Reflexion</span><span class="sxs-lookup"><span data-stu-id="d6966-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
- [<span data-ttu-id="d6966-128">Anzeigen von Typinformationen</span><span class="sxs-lookup"><span data-stu-id="d6966-128">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)
- [<span data-ttu-id="d6966-129">Reflektion und generische Typen</span><span class="sxs-lookup"><span data-stu-id="d6966-129">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- <xref:System.Reflection.Emit>
- [<span data-ttu-id="d6966-130">Abrufen von Informationen aus Attributen</span><span class="sxs-lookup"><span data-stu-id="d6966-130">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)

## <a name="see-also"></a><span data-ttu-id="d6966-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6966-131">See also</span></span>

- [<span data-ttu-id="d6966-132">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d6966-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d6966-133">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="d6966-133">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
