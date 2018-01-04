---
title: 'Vorgehensweise: Auflisten von auf einem Computer vorhandenen Zeitzonen'
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2318a42040388adfe327f9d0075754daa1aa22a6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="d62c2-102">Vorgehensweise: Auflisten von auf einem Computer vorhandenen Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="d62c2-102">How to: Enumerate time zones present on a computer</span></span>

<span data-ttu-id="d62c2-103">Für die erfolgreiche Verarbeitung einer Zeitzone ist es erforderlich, dass dem System Informationen zu dieser Zeitzone zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="d62c2-103">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="d62c2-104">Die Betriebssysteme Windows XP und Windows Vista speichert diese Informationen in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="d62c2-104">The Windows XP and Windows Vista operating systems store this information in the registry.</span></span> <span data-ttu-id="d62c2-105">Es gibt zwar sehr viele Zeitzonen auf der Welt, die Registrierung enthält aber nur Informationen zu einigen davon.</span><span class="sxs-lookup"><span data-stu-id="d62c2-105">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="d62c2-106">Darüber hinaus ist die Registrierung selbst eine dynamische Struktur, deren Inhalt absichtlich oder aus Versehen geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d62c2-106">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="d62c2-107">Daher kann eine Anwendung nicht voraussetzen, dass eine bestimmte Zeitzone in einem System definiert und verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d62c2-107">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="d62c2-108">Bei vielen Anwendungen, die Zeitzoneninformationen verwenden, besteht der erste Schritt darin zu ermitteln, ob die erforderlichen Zeitzonen im lokalen System verfügbar sind, oder dem Benutzer eine Liste der Zeitzonen zur Auswahl zu bieten.</span><span class="sxs-lookup"><span data-stu-id="d62c2-108">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="d62c2-109">Dafür wiederum muss eine Anwendung die im lokalen System definierten Zeitzonen aufzählen können.</span><span class="sxs-lookup"><span data-stu-id="d62c2-109">This requires that an application enumerate the time zones defined on a local system.</span></span>

> [!NOTE]
> <span data-ttu-id="d62c2-110">Wenn eine Anwendung auf dem Vorhandensein einer bestimmten Zeitzone, die nicht in einem lokalen System definiert werden kann benötigt, kann das Vorhandensein von die Anwendung sichergestellt werden, werden serialisieren und Deserialisieren von Informationen über die Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="d62c2-110">If an application relies on the presence of a particular time zone that may not be defined on a local system, the application can ensure its presence by serializing and deserializing information about the time zone.</span></span> <span data-ttu-id="d62c2-111">Die Zeitzone kann ein Listenfeld-Steuerelement dann hinzugefügt werden, damit Benutzer der Anwendung, die sie auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="d62c2-111">The time zone can then be added to a list control so that the application user can select it.</span></span> <span data-ttu-id="d62c2-112">Weitere Informationen finden Sie unter [wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) und [Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="d62c2-112">For details, see [How to: Save Time Zones to an Embedded Resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) and [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span></span>

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="d62c2-113">Aufzählen der im lokalen System vorhandenen Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="d62c2-113">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="d62c2-114">Rufen Sie die <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="d62c2-114">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d62c2-115">Die Methode gibt eine generische <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Auflistung von <xref:System.TimeZoneInfo> Objekte.</span><span class="sxs-lookup"><span data-stu-id="d62c2-115">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span> <span data-ttu-id="d62c2-116">Die Einträge in der Auflistung sind sortiert nach ihren <xref:System.TimeZoneInfo.DisplayName%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d62c2-116">The entries in the collection are sorted by their <xref:System.TimeZoneInfo.DisplayName%2A> property.</span></span> <span data-ttu-id="d62c2-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d62c2-117">For example:</span></span>

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. <span data-ttu-id="d62c2-118">Auflisten die einzelnen <xref:System.TimeZoneInfo> Objekte in der Auflistung mithilfe einer `foreach` -Schleife (in c#) oder eine `For Each`...`Next`</span><span class="sxs-lookup"><span data-stu-id="d62c2-118">Enumerate the individual <xref:System.TimeZoneInfo> objects in the collection by using a `foreach` loop (in C#) or a `For Each`…`Next`</span></span> <span data-ttu-id="d62c2-119">(in Visual Basic)-Schleife aus, und führen Sie alle erforderlichen Verarbeitungsschritte für jedes Objekt.</span><span class="sxs-lookup"><span data-stu-id="d62c2-119">loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="d62c2-120">Z. B. der folgende Code Listet die <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Auflistung von <xref:System.TimeZoneInfo> Objekte zurückgegebenen in Schritt 1 und der Anzeigename der einzelnen Zeitzonen in der Konsole aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d62c2-120">For example, the following code enumerates the <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a><span data-ttu-id="d62c2-121">Den Benutzer mit einer Liste der auf dem lokalen System enthaltenen Zeitzonen dar</span><span class="sxs-lookup"><span data-stu-id="d62c2-121">To present the user with a list of time zones present on the local system</span></span>

1. <span data-ttu-id="d62c2-122">Rufen Sie die <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="d62c2-122">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d62c2-123">Die Methode gibt eine generische <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Auflistung von <xref:System.TimeZoneInfo> Objekte.</span><span class="sxs-lookup"><span data-stu-id="d62c2-123">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span>

2. <span data-ttu-id="d62c2-124">Weisen Sie in Schritt 1 zurückgegebene Auflistung der `DataSource` Eigenschaft einer Windows Forms- oder ASP.NET-ANWENDUNGEN Listensteuerelement.</span><span class="sxs-lookup"><span data-stu-id="d62c2-124">Assign the collection returned in step 1 to the `DataSource` property of a Windows forms or ASP.NET list control.</span></span>

3. <span data-ttu-id="d62c2-125">Abrufen der <xref:System.TimeZoneInfo> -Objekt, das der Benutzer ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="d62c2-125">Retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span>

<span data-ttu-id="d62c2-126">Das Beispiel enthält ein Beispiel für eine Windows-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d62c2-126">The example provides an illustration for a Windows application.</span></span>

## <a name="example"></a><span data-ttu-id="d62c2-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d62c2-127">Example</span></span>

<span data-ttu-id="d62c2-128">Das Beispiel startet eine Windows-Anwendung, die auf einem System in einem Listenfeld definierten Zeitzonen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d62c2-128">The example starts a Windows application that displays the time zones defined on a system in a list box.</span></span> <span data-ttu-id="d62c2-129">Im Beispiel zeigt ein Dialogfeld mit dem Wert der dann an die <xref:System.TimeZoneInfo.DisplayName%2A> -Eigenschaft des vom Benutzer ausgewählten Zeitzone-Objekts.</span><span class="sxs-lookup"><span data-stu-id="d62c2-129">The example then displays a dialog box that contains the value of the <xref:System.TimeZoneInfo.DisplayName%2A> property of the time zone object selected by the user.</span></span>

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

<span data-ttu-id="d62c2-130">Die meisten Listensteuerelemente (z. B. die <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> oder <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> Steuerelement) ermöglichen es Ihnen, eine Auflistung von Objektvariablen zuweisen ihre `DataSource` Eigenschaft solange diese Auflistung implementiert die <xref:System.Collections.IEnumerable> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d62c2-130">Most list controls (such as the <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> or <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> control) allow you to assign a collection of object variables to their `DataSource` property as long as that collection implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="d62c2-131">(Die generische <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> Klasse hierzu.) Um ein einzelnes Objekt in der Auflistung anzuzeigen, ruft das Steuerelement des Objekts `ToString` Methode, um die Zeichenfolge zu extrahieren, die verwendet wird, um das Objekt darstellen.</span><span class="sxs-lookup"><span data-stu-id="d62c2-131">(The generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class does this.) To display an individual object in the collection, the control calls that object's `ToString` method to extract the string that is used to represent the object.</span></span> <span data-ttu-id="d62c2-132">Im Fall von <xref:System.TimeZoneInfo> Objekte, die `ToString` Methode gibt die <xref:System.TimeZoneInfo> Anzeigename des Objekts (der Wert des seine <xref:System.TimeZoneInfo.DisplayName%2A> Eigenschaft).</span><span class="sxs-lookup"><span data-stu-id="d62c2-132">In the case of <xref:System.TimeZoneInfo> objects, the `ToString` method returns the <xref:System.TimeZoneInfo> object's display name (the value of its <xref:System.TimeZoneInfo.DisplayName%2A> property).</span></span>

> [!NOTE]
> <span data-ttu-id="d62c2-133">Da List-Steuerelemente des Objekts aufrufen `ToString` -Methode, können Sie eine Auflistung von zuweisen <xref:System.TimeZoneInfo> Objekte an das Steuerelement, damit das Steuerelement einen aussagekräftigen Namen für jedes Objekt anzeigen und Abrufen der <xref:System.TimeZoneInfo> -Objekt, das der Benutzer ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="d62c2-133">Because list controls call an object's `ToString` method, you can assign a collection of <xref:System.TimeZoneInfo> objects to the control, have the control display a meaningful name for each object, and retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span> <span data-ttu-id="d62c2-134">Hierdurch entfällt die Notwendigkeit, eine Zeichenfolge für jedes Objekt in der Auflistung zu extrahieren, weisen Sie die Zeichenfolge für eine Sammlung, die wiederum an des Steuerelements zugewiesen ist `DataSource` -Eigenschaft, rufen Sie die Zeichenfolge, die der Benutzer ausgewählt hat, und klicken Sie dann diese Zeichenfolge verwenden, um das Objekt zu extrahieren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d62c2-134">This eliminates the need to extract a string for each object in the collection, assign the string to a collection that is in turn assigned to the control's `DataSource` property, retrieve the string the user has selected, and then use this string to extract the object that it describes.</span></span> 

## <a name="compiling-the-code"></a><span data-ttu-id="d62c2-135">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d62c2-135">Compiling the code</span></span>

<span data-ttu-id="d62c2-136">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d62c2-136">This example requires:</span></span>

* <span data-ttu-id="d62c2-137">Dem Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d62c2-137">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="d62c2-138">Dass die folgenden Namespaces importiert werden:</span><span class="sxs-lookup"><span data-stu-id="d62c2-138">That the following namespaces be imported:</span></span>

  <span data-ttu-id="d62c2-139"><xref:System>(in C#-Code)</span><span class="sxs-lookup"><span data-stu-id="d62c2-139"><xref:System> (in C# code)</span></span>

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a><span data-ttu-id="d62c2-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d62c2-140">See also</span></span>

<span data-ttu-id="d62c2-141">[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="d62c2-141">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span></span>
