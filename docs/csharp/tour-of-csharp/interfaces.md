---
title: "C#-Schnittstellen – Überblick über C#"
description: "Schnittstellen definieren von Typen in C# implementierte Verträge."
keywords: .NET, Csharp, Schnittstellen, Mehrfachvererbung, Polymorphie
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a9bf82f4-efd1-4216-bd34-4ef0fa48c968
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 673ac56f3f5732fcda02d313b6f4273708ae365f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="interfaces"></a><span data-ttu-id="d1972-104">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d1972-104">Interfaces</span></span>

<span data-ttu-id="d1972-105">Eine ***Schnittstelle*** definiert einen Vertrag, der von Klassen und Strukturen implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d1972-105">An ***interface*** defines a contract that can be implemented by classes and structs.</span></span> <span data-ttu-id="d1972-106">Eine Schnittstelle kann Methoden, Eigenschaften, Ereignisse und Indexer enthalten.</span><span class="sxs-lookup"><span data-stu-id="d1972-106">An interface can contain methods, properties, events, and indexers.</span></span> <span data-ttu-id="d1972-107">Eine Schnittstelle stellt keine Implementierungen der von ihr definierten Member bereit. Sie gibt lediglich die Member an, die von Klassen oder Strukturen bereitgestellt werden müssen, die die Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="d1972-107">An interface does not provide implementations of the members it defines—it merely specifies the members that must be supplied by classes or structs that implement the interface.</span></span>

<span data-ttu-id="d1972-108">Schnittstellen können ***Mehrfachvererbung*** einsetzen.</span><span class="sxs-lookup"><span data-stu-id="d1972-108">Interfaces may employ ***multiple inheritance***.</span></span> <span data-ttu-id="d1972-109">Im folgenden Beispiel erbt die Schnittstelle `IComboBox` sowohl von `ITextBox` als auch `IListBox`.</span><span class="sxs-lookup"><span data-stu-id="d1972-109">In the following example, the interface `IComboBox` inherits from both `ITextBox` and `IListBox`.</span></span>

<span data-ttu-id="d1972-110">[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]</span><span class="sxs-lookup"><span data-stu-id="d1972-110">[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]</span></span>

<span data-ttu-id="d1972-111">Klassen und Strukturen können mehrere Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="d1972-111">Classes and structs can implement multiple interfaces.</span></span> <span data-ttu-id="d1972-112">Im folgenden Beispiel implementiert die Klasse `EditBox` sowohl `IControl` als auch `IDataBound`.</span><span class="sxs-lookup"><span data-stu-id="d1972-112">In the following example, the class `EditBox` implements both `IControl` and `IDataBound`.</span></span>

<span data-ttu-id="d1972-113">[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]</span><span class="sxs-lookup"><span data-stu-id="d1972-113">[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]</span></span>

<span data-ttu-id="d1972-114">Wenn eine Klasse oder Struktur eine bestimmte Schnittstelle implementiert, können Instanzen dieser Klasse oder Struktur implizit in diesen Schnittstellentyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="d1972-114">When a class or struct implements a particular interface, instances of that class or struct can be implicitly converted to that interface type.</span></span> <span data-ttu-id="d1972-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d1972-115">For example</span></span>

<span data-ttu-id="d1972-116">[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]</span><span class="sxs-lookup"><span data-stu-id="d1972-116">[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]</span></span>

<span data-ttu-id="d1972-117">In Fällen, in denen nicht bekannt ist, dass eine Instanz eine bestimmte Schnittstelle implementiert, können dynamische Typumwandlungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d1972-117">In cases where an instance is not statically known to implement a particular interface, dynamic type casts can be used.</span></span> <span data-ttu-id="d1972-118">Beispielsweise verwenden die folgenden Anweisungen dynamische Typumwandlungen zum Abrufen der `IControl`- und `IDataBound`-Schnittstellenimplementierungen eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="d1972-118">For example, the following statements use dynamic type casts to obtain an object’s `IControl` and `IDataBound` interface implementations.</span></span> <span data-ttu-id="d1972-119">Da der eigentliche Laufzeittyp des Objekts `EditBox` ist, sind die Umwandlungen erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d1972-119">Because the run-time actual type of the object is `EditBox`, the casts succeed.</span></span>

<span data-ttu-id="d1972-120">[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]</span><span class="sxs-lookup"><span data-stu-id="d1972-120">[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]</span></span>

<span data-ttu-id="d1972-121">In der vorherigen `EditBox`-Klasse werden die `Paint`-Methode aus der `IControl`-Schnittstelle und die `Bind`-Methode aus der `IDataBound`-Schnittstelle mithilfe öffentlicher Member implementiert.</span><span class="sxs-lookup"><span data-stu-id="d1972-121">In the previous `EditBox` class, the `Paint` method from the `IControl` interface and the `Bind` method from the `IDataBound` interface are implemented using public members.</span></span> <span data-ttu-id="d1972-122">C# unterstützt außerdem explizite ***Implementierungen eines Schnittstellenmembers***, sodass die Klasse oder Struktur vermeiden können, die Member öffentlich zu machen.</span><span class="sxs-lookup"><span data-stu-id="d1972-122">C# also supports explicit ***interface member implementations***, enabling the class or struct to avoid making the members public.</span></span> <span data-ttu-id="d1972-123">Eine explizite Implementierung eines Schnittstellenmembers wird mit dem vollqualifizierten Namen des Schnittstellenmembers geschrieben.</span><span class="sxs-lookup"><span data-stu-id="d1972-123">An explicit interface member implementation is written using the fully qualified interface member name.</span></span> <span data-ttu-id="d1972-124">Die `EditBox`-Klasse könnte z.B. die `IControl.Paint`- und `IDataBound.Bind`-Methode wie folgt über explizite Implementierungen eines Schnittstellenmembers implementieren.</span><span class="sxs-lookup"><span data-stu-id="d1972-124">For example, the `EditBox` class could implement the `IControl.Paint` and `IDataBound.Bind` methods using explicit interface member implementations as follows.</span></span>

<span data-ttu-id="d1972-125">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]</span><span class="sxs-lookup"><span data-stu-id="d1972-125">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]</span></span>

<span data-ttu-id="d1972-126">Der Zugriff auf explizite Schnittstellenmember kann nur über den Schnittstellentyp erfolgen.</span><span class="sxs-lookup"><span data-stu-id="d1972-126">Explicit interface members can only be accessed via the interface type.</span></span> <span data-ttu-id="d1972-127">Die von der vorherigen EditBox-Klasse bereitgestellte Implementierung von `IControl.Paint` kann z.B. nur aufgerufen werden, indem zuerst der `EditBox`-Verweis in den `IControl`-Schnittstellentyp konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="d1972-127">For example, the implementation of `IControl.Paint` provided by the previous EditBox class can only be invoked by first converting the `EditBox` reference to the `IControl` interface type.</span></span>

<span data-ttu-id="d1972-128">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]</span><span class="sxs-lookup"><span data-stu-id="d1972-128">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="d1972-129">[Zurück](arrays.md)
[Weiter](enums.md)</span><span class="sxs-lookup"><span data-stu-id="d1972-129">[Previous](arrays.md)
[Next](enums.md)</span></span>

