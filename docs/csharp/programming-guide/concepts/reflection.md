---
title: Reflexion (C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: a56fb24b63e4d80dbb67b079466b67cd11672023
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74711658"
---
# <a name="reflection-c"></a><span data-ttu-id="26666-102">Reflexion (C#)</span><span class="sxs-lookup"><span data-stu-id="26666-102">Reflection (C#)</span></span>

<span data-ttu-id="26666-103">Reflexion bietet Objekte (des Typs <xref:System.Type>), die Assemblys, Module und Typen beschreiben.</span><span class="sxs-lookup"><span data-stu-id="26666-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules, and types.</span></span> <span data-ttu-id="26666-104">Mithilfe von Reflexion können Sie dynamisch eine Instanz eines Typs erzeugen, den Typ an ein vorhandenes Objekt binden und Typinformationen von vorhandenen Objekten abfragen. Ebenso wird erläutert wie die Methoden vorhandener Objekte aufgerufen und auf ihre Felder und Eigenschaften zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="26666-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="26666-105">Wenn Sie Attribute in Ihrem Code verwenden, können Sie mit Reflexion auf diese zugreifen.</span><span class="sxs-lookup"><span data-stu-id="26666-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="26666-106">Weitere Informationen finden Sie unter [Attribute](../../../standard/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="26666-106">For more information, see [Attributes](../../../standard/attributes/index.md).</span></span>

<span data-ttu-id="26666-107">Hier sehen Sie ein einfaches Beispiel für Reflexion mit der Methode <xref:System.Object.GetType>, die von allen Typen der Basisklasse `Object` geerbt wird, zum Abrufen von Typinformationen einer Variable:</span><span class="sxs-lookup"><span data-stu-id="26666-107">Here's a simple example of reflection using the <xref:System.Object.GetType> method - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>

> [!NOTE]
> <span data-ttu-id="26666-108">Stellen Sie sicher, dass Sie `using System;` und `using System.Reflection;` am Anfang Ihrer *.cs*-Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="26666-108">Make sure you add `using System;` and `using System.Reflection;` at the top of your *.cs* file.</span></span>

```csharp
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type);
```

<span data-ttu-id="26666-109">Die Ausgabe ist: `System.Int32`.</span><span class="sxs-lookup"><span data-stu-id="26666-109">The output is: `System.Int32`.</span></span>

<span data-ttu-id="26666-110">Im folgenden Beispiel wird Reflexion verwendet, um den vollständigen Namen der geladenen Assembly abzurufen.</span><span class="sxs-lookup"><span data-stu-id="26666-110">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>

```csharp
// Using Reflection to get information of an Assembly:
Assembly info = typeof(int).Assembly;
Console.WriteLine(info);
```

<span data-ttu-id="26666-111">Die Ausgabe ist: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span><span class="sxs-lookup"><span data-stu-id="26666-111">The output is: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span></span>

> [!NOTE]
> <span data-ttu-id="26666-112">Die C#-Schlüsselwörter `protected` und `internal` haben in IL keine Bedeutung und werden nicht in Reflexions-APIs verwendet.</span><span class="sxs-lookup"><span data-stu-id="26666-112">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="26666-113">Die entsprechenden Begriffe in IL sind *Family* und *Assembly*.</span><span class="sxs-lookup"><span data-stu-id="26666-113">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="26666-114">Verwenden Sie zum Identifizieren einer `internal`-Methode mithilfe von Reflexion die Eigenschaft <xref:System.Reflection.MethodBase.IsAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="26666-114">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="26666-115">Verwenden Sie `protected internal` zum Identifizieren einer Methode <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="26666-115">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>

## <a name="reflection-overview"></a><span data-ttu-id="26666-116">Übersicht über Reflexion</span><span class="sxs-lookup"><span data-stu-id="26666-116">Reflection overview</span></span>

<span data-ttu-id="26666-117">Reflexion ist in folgenden Situationen nützlich:</span><span class="sxs-lookup"><span data-stu-id="26666-117">Reflection is useful in the following situations:</span></span>

- <span data-ttu-id="26666-118">Wenn Sie in den Metadaten Ihres Programms auf Attribute zugreifen müssen</span><span class="sxs-lookup"><span data-stu-id="26666-118">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="26666-119">Weitere Informationen finden Sie unter [Abrufen von Informationen aus Attributen](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="26666-119">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>
- <span data-ttu-id="26666-120">Zum Untersuchen und Instanziieren von Typen in einer Assembly</span><span class="sxs-lookup"><span data-stu-id="26666-120">For examining and instantiating types in an assembly.</span></span>
- <span data-ttu-id="26666-121">Zum Erstellen neuer Typen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="26666-121">For building new types at runtime.</span></span> <span data-ttu-id="26666-122">Verwenden Sie Klassen in <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="26666-122">Use classes in <xref:System.Reflection.Emit>.</span></span>
- <span data-ttu-id="26666-123">Zum Ausführen von spätem Binden mit Zugriff auf Methoden der zur Laufzeit erstellten Typen</span><span class="sxs-lookup"><span data-stu-id="26666-123">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="26666-124">Weitere Informationen finden Sie im Thema [Dynamisches Laden und Verwenden von Typen](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="26666-124">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>

## <a name="related-sections"></a><span data-ttu-id="26666-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="26666-125">Related sections</span></span>

<span data-ttu-id="26666-126">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="26666-126">For more information:</span></span>

- [<span data-ttu-id="26666-127">Reflexion</span><span class="sxs-lookup"><span data-stu-id="26666-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
- [<span data-ttu-id="26666-128">Anzeigen von Typinformationen</span><span class="sxs-lookup"><span data-stu-id="26666-128">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)
- [<span data-ttu-id="26666-129">Reflexion und generische Typen</span><span class="sxs-lookup"><span data-stu-id="26666-129">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- <xref:System.Reflection.Emit>
- [<span data-ttu-id="26666-130">Abrufen von Informationen aus Attributen</span><span class="sxs-lookup"><span data-stu-id="26666-130">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)

## <a name="see-also"></a><span data-ttu-id="26666-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26666-131">See also</span></span>

- [<span data-ttu-id="26666-132">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="26666-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="26666-133">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="26666-133">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
