---
title: "Gewusst wie: Aufzählen der auf einem Computer vorhandenen Zeitzonen"
description: "Aufzählen der auf einem Computer vorhandenen Zeitzonen"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c5ae4a6c-1790-4355-b5b1-879aaf956129
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f30ba2a483ff7e5867417969946c2774175d5e3d
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="b77c5-104">Gewusst wie: Aufzählen der auf einem Computer vorhandenen Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="b77c5-104">How to: enumerate time zones present on a computer</span></span>

<span data-ttu-id="b77c5-105">Für die erfolgreiche Verarbeitung einer Zeitzone ist es erforderlich, dass dem System Informationen zu dieser Zeitzone zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="b77c5-105">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="b77c5-106">Windows-Betriebssysteme beispielsweise speichern diese Informationen in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="b77c5-106">For example, the Windows operating system stores this information in the registry.</span></span> <span data-ttu-id="b77c5-107">Es gibt zwar sehr viele Zeitzonen auf der Welt, die Registrierung enthält aber nur Informationen zu einigen davon.</span><span class="sxs-lookup"><span data-stu-id="b77c5-107">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="b77c5-108">Darüber hinaus ist die Registrierung selbst eine dynamische Struktur, deren Inhalt absichtlich oder aus Versehen geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b77c5-108">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="b77c5-109">Daher kann eine Anwendung nicht voraussetzen, dass eine bestimmte Zeitzone in einem System definiert und verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b77c5-109">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="b77c5-110">Bei vielen Anwendungen, die Zeitzoneninformationen verwenden, besteht der erste Schritt darin zu ermitteln, ob die erforderlichen Zeitzonen im lokalen System verfügbar sind, oder dem Benutzer eine Liste der Zeitzonen zur Auswahl zu bieten.</span><span class="sxs-lookup"><span data-stu-id="b77c5-110">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="b77c5-111">Dafür wiederum muss eine Anwendung die im lokalen System definierten Zeitzonen aufzählen können.</span><span class="sxs-lookup"><span data-stu-id="b77c5-111">This requires that an application enumerate the time zones defined on a local system.</span></span> 

## <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="b77c5-112">Aufzählen der im lokalen System vorhandenen Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="b77c5-112">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="b77c5-113">Rufen Sie die [TimeZoneInfo.GetSystemTimeZones](xref:System.TimeZoneInfo.GetSystemTimeZones)-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="b77c5-113">Call the [TimeZoneInfo.GetSystemTimeZones](xref:System.TimeZoneInfo.GetSystemTimeZones) method.</span></span> <span data-ttu-id="b77c5-114">Die Methode gibt eine allgemeine [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601)-Auflistung von [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekten zurück.</span><span class="sxs-lookup"><span data-stu-id="b77c5-114">The method returns a generic [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) collection of [TimeZoneInfo](xref:System.TimeZoneInfo) objects.</span></span> <span data-ttu-id="b77c5-115">Die Einträge in der Auflistung sind nach ihrer [DisplayName](xref:System.TimeZoneInfo.DisplayName)-Eigenschaft sortiert.</span><span class="sxs-lookup"><span data-stu-id="b77c5-115">The entries in the collection are sorted by their [DisplayName](xref:System.TimeZoneInfo.DisplayName) property.</span></span> <span data-ttu-id="b77c5-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b77c5-116">For example:</span></span>

    ```csharp
    ReadOnlyCollection<TimeZoneInfo> tzCollection;
    tzCollection = TimeZoneInfo.GetSystemTimeZones();
    ```

    ```vb
    Dim tzCollection As ReadOnlyCollection(Of TimeZoneInfo) = TimeZoneInfo.GetSystemTimeZones
    ```

2. <span data-ttu-id="b77c5-117">Zählen Sie die einzelnen [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekte in der Auflistung auf, indem Sie eine `foreach`-Schleife (in C#) oder eine `For Each…Next`-Schleife (in Visual Basic) verwenden und alle erforderlichen Verarbeitungsschritte für jedes Objekt ausführen.</span><span class="sxs-lookup"><span data-stu-id="b77c5-117">Enumerate the individual [TimeZoneInfo](xref:System.TimeZoneInfo) objects in the collection by using a `foreach` loop (in C#) or a `For Each…Next` loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="b77c5-118">Der folgende Code zählt beispielsweise die [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601)-Auflistung von [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekten auf, die in Schritt 1 zurückgegeben wurden, und gibt den Anzeigenamen jeder Zeitzone in der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="b77c5-118">For example, the following code enumerates the [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) collection of [TimeZoneInfo](xref:System.TimeZoneInfo) objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

    ```csharp
    foreach (TimeZoneInfo timeZone in tzCollection)
    Console.WriteLine("   {0}: {1}", timeZone.Id, timeZone.DisplayName);
    ```

    ```vb
    For Each timeZone As TimeZoneInfo In tzCollection
        Console.WriteLine("   {0}: {1}", timeZone.Id, timeZone.DisplayName)
    Next
    ```

## <a name="see-also"></a><span data-ttu-id="b77c5-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b77c5-119">See Also</span></span>

[<span data-ttu-id="b77c5-120">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="b77c5-120">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="b77c5-121">Suchen der in einem lokalen System definierten Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="b77c5-121">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)


