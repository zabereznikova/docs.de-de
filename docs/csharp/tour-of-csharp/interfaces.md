---
title: C#-Schnittstellen – Überblick über C#
description: Schnittstellen definieren von Typen in C# implementierte Verträge.
ms.date: 08/10/2016
ms.assetid: a9bf82f4-efd1-4216-bd34-4ef0fa48c968
ms.openlocfilehash: d10d9f69cebe9a05cdff9b9ff5d817237bf8c56f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346838"
---
# <a name="interfaces"></a><span data-ttu-id="b4768-103">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b4768-103">Interfaces</span></span>

<span data-ttu-id="b4768-104">Eine ***Schnittstelle*** definiert einen Vertrag, der von Klassen und Strukturen implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b4768-104">An ***interface*** defines a contract that can be implemented by classes and structs.</span></span> <span data-ttu-id="b4768-105">Eine Schnittstelle kann Methoden, Eigenschaften, Ereignisse und Indexer enthalten.</span><span class="sxs-lookup"><span data-stu-id="b4768-105">An interface can contain methods, properties, events, and indexers.</span></span> <span data-ttu-id="b4768-106">Eine Schnittstelle stellt keine Implementierungen der von ihr definierten Member bereit. Sie gibt lediglich die Member an, die von Klassen oder Strukturen bereitgestellt werden müssen, die die Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="b4768-106">An interface does not provide implementations of the members it defines—it merely specifies the members that must be supplied by classes or structs that implement the interface.</span></span>

<span data-ttu-id="b4768-107">Schnittstellen können ***Mehrfachvererbung*** einsetzen.</span><span class="sxs-lookup"><span data-stu-id="b4768-107">Interfaces may employ ***multiple inheritance***.</span></span> <span data-ttu-id="b4768-108">Im folgenden Beispiel erbt die Schnittstelle `IComboBox` sowohl von `ITextBox` als auch `IListBox`.</span><span class="sxs-lookup"><span data-stu-id="b4768-108">In the following example, the interface `IComboBox` inherits from both `ITextBox` and `IListBox`.</span></span>

[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]

<span data-ttu-id="b4768-109">Klassen und Strukturen können mehrere Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="b4768-109">Classes and structs can implement multiple interfaces.</span></span> <span data-ttu-id="b4768-110">Im folgenden Beispiel implementiert die Klasse `EditBox` sowohl `IControl` als auch `IDataBound`.</span><span class="sxs-lookup"><span data-stu-id="b4768-110">In the following example, the class `EditBox` implements both `IControl` and `IDataBound`.</span></span>

[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]

<span data-ttu-id="b4768-111">Wenn eine Klasse oder Struktur eine bestimmte Schnittstelle implementiert, können Instanzen dieser Klasse oder Struktur implizit in diesen Schnittstellentyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="b4768-111">When a class or struct implements a particular interface, instances of that class or struct can be implicitly converted to that interface type.</span></span> <span data-ttu-id="b4768-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b4768-112">For example</span></span>

[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]

<span data-ttu-id="b4768-113">In Fällen, in denen nicht bekannt ist, dass eine Instanz eine bestimmte Schnittstelle implementiert, können dynamische Typumwandlungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4768-113">In cases where an instance is not statically known to implement a particular interface, dynamic type casts can be used.</span></span> <span data-ttu-id="b4768-114">Beispielsweise verwenden die folgenden Anweisungen dynamische Typumwandlungen zum Abrufen der `IControl`- und `IDataBound`-Schnittstellenimplementierungen eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="b4768-114">For example, the following statements use dynamic type casts to obtain an object’s `IControl` and `IDataBound` interface implementations.</span></span> <span data-ttu-id="b4768-115">Da der eigentliche Laufzeittyp des Objekts `EditBox` ist, sind die Umwandlungen erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="b4768-115">Because the run-time actual type of the object is `EditBox`, the casts succeed.</span></span>

[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]

<span data-ttu-id="b4768-116">In der vorherigen `EditBox`-Klasse werden die `Paint`-Methode aus der `IControl`-Schnittstelle und die `Bind`-Methode aus der `IDataBound`-Schnittstelle mithilfe öffentlicher Member implementiert.</span><span class="sxs-lookup"><span data-stu-id="b4768-116">In the previous `EditBox` class, the `Paint` method from the `IControl` interface and the `Bind` method from the `IDataBound` interface are implemented using public members.</span></span> <span data-ttu-id="b4768-117">C# unterstützt außerdem explizite ***Implementierungen eines Schnittstellenmembers***, sodass die Klasse oder Struktur vermeiden können, die Member öffentlich zu machen.</span><span class="sxs-lookup"><span data-stu-id="b4768-117">C# also supports explicit ***interface member implementations***, enabling the class or struct to avoid making the members public.</span></span> <span data-ttu-id="b4768-118">Eine explizite Implementierung eines Schnittstellenmembers wird mit dem vollqualifizierten Namen des Schnittstellenmembers geschrieben.</span><span class="sxs-lookup"><span data-stu-id="b4768-118">An explicit interface member implementation is written using the fully qualified interface member name.</span></span> <span data-ttu-id="b4768-119">Die `EditBox`-Klasse könnte z.B. die `IControl.Paint`- und `IDataBound.Bind`-Methode wie folgt über explizite Implementierungen eines Schnittstellenmembers implementieren.</span><span class="sxs-lookup"><span data-stu-id="b4768-119">For example, the `EditBox` class could implement the `IControl.Paint` and `IDataBound.Bind` methods using explicit interface member implementations as follows.</span></span>

[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]

<span data-ttu-id="b4768-120">Der Zugriff auf explizite Schnittstellenmember kann nur über den Schnittstellentyp erfolgen.</span><span class="sxs-lookup"><span data-stu-id="b4768-120">Explicit interface members can only be accessed via the interface type.</span></span> <span data-ttu-id="b4768-121">Die von der vorherigen EditBox-Klasse bereitgestellte Implementierung von `IControl.Paint` kann z.B. nur aufgerufen werden, indem zuerst der `EditBox`-Verweis in den `IControl`-Schnittstellentyp konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="b4768-121">For example, the implementation of `IControl.Paint` provided by the previous EditBox class can only be invoked by first converting the `EditBox` reference to the `IControl` interface type.</span></span>

[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]

>[!div class="step-by-step"]
><span data-ttu-id="b4768-122">[Zurück](arrays.md)
>[Weiter](delegates.md)</span><span class="sxs-lookup"><span data-stu-id="b4768-122">[Previous](arrays.md)
[Next](delegates.md)</span></span>
