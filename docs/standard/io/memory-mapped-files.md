---
title: Speicherabbilddateien
description: Erfahren Sie mehr über Speicherabbilddateien in .NET. Diese Dateien enthalten Dateiinhalte in virtuellem Arbeitsspeicher und ermöglichen Anwendungen das Ändern der Datei durch direktes Schreiben in den Arbeitsspeicher.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- memory-mapped files
- inter-process communication
ms.assetid: a483d1b5-64aa-45b6-86ef-11b859f7f02e
ms.openlocfilehash: dc0da9842df7b0a827293c42d80ccdd418a043b2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819200"
---
# <a name="memory-mapped-files"></a><span data-ttu-id="30870-103">Im Speicher abgebildete Dateien</span><span class="sxs-lookup"><span data-stu-id="30870-103">Memory-mapped files</span></span>

<span data-ttu-id="30870-104">Eine Speicherabbilddatei enthält den Inhalt einer Datei im virtuellen Speicher.</span><span class="sxs-lookup"><span data-stu-id="30870-104">A memory-mapped file contains the contents of a file in virtual memory.</span></span> <span data-ttu-id="30870-105">Diese Zuordnung zwischen einer Datei und Speicherplatz ermöglicht es einer Anwendung mit mehreren Prozessen, die Datei durch direktes Lesen und Schreiben im Arbeitsspeicher zu ändern.</span><span class="sxs-lookup"><span data-stu-id="30870-105">This mapping between a file and memory space enables an application, including multiple processes, to modify the file by reading and writing directly to the memory.</span></span> <span data-ttu-id="30870-106">Sie können verwalteten Code verwenden, um auf die gleiche Weise auf im Speicher abgebildete Dateien zuzugreifen wie native Windows-Funktionen. Dies wird unter [Verwalten von im Speicher abgebildeten Dateien](/previous-versions/ms810613(v=msdn.10)) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="30870-106">You can use managed code to access memory-mapped files in the same way that native Windows functions access memory-mapped files, as described in [Managing Memory-Mapped Files](/previous-versions/ms810613(v=msdn.10)).</span></span>  
  
<span data-ttu-id="30870-107">Es gibt zwei Arten von Speicherabbilddateien:</span><span class="sxs-lookup"><span data-stu-id="30870-107">There are two types of memory-mapped files:</span></span>  
  
- <span data-ttu-id="30870-108">Beibehaltene Speicherabbilddateien</span><span class="sxs-lookup"><span data-stu-id="30870-108">Persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="30870-109">Persistent gespeicherte Dateien sind Speicherabbilddateien, die einer Quelldatei auf einem Datenträger zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="30870-109">Persisted files are memory-mapped files that are associated with a source file on a disk.</span></span> <span data-ttu-id="30870-110">Wenn der letzte Prozess die Verwendung der Datei beendet, werden die Daten in der Quelldatei auf dem Datenträger gespeichert.</span><span class="sxs-lookup"><span data-stu-id="30870-110">When the last process has finished working with the file, the data is saved to the source file on the disk.</span></span> <span data-ttu-id="30870-111">Diese Speicherabbilddateien eignen sich für extrem große Quelldateien.</span><span class="sxs-lookup"><span data-stu-id="30870-111">These memory-mapped files are suitable for working with extremely large source files.</span></span>  
  
- <span data-ttu-id="30870-112">Nicht beibehaltene Speicherabbilddateien</span><span class="sxs-lookup"><span data-stu-id="30870-112">Non-persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="30870-113">Nicht persistent gespeicherte Dateien sind Speicherabbilddateien, die keiner Datei auf einem Datenträger zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="30870-113">Non-persisted files are memory-mapped files that are not associated with a file on a disk.</span></span> <span data-ttu-id="30870-114">Wenn der letzte Prozess die Verwendung der Datei beendet, gehen die Daten verloren, und die Datei wird von der Garbage Collection freigegeben.</span><span class="sxs-lookup"><span data-stu-id="30870-114">When the last process has finished working with the file, the data is lost and the file is reclaimed by garbage collection.</span></span> <span data-ttu-id="30870-115">Diese Dateien eignen sich zum Erstellen von freigegebenen Speicherbereichen für die prozessübergreifende Kommunikation (IPC).</span><span class="sxs-lookup"><span data-stu-id="30870-115">These files are suitable for creating shared memory for inter-process communications (IPC).</span></span>  
  
## <a name="processes-views-and-managing-memory"></a><span data-ttu-id="30870-116">Prozesse, Ansichten und Verwalten des Arbeitsspeichers</span><span class="sxs-lookup"><span data-stu-id="30870-116">Processes, Views, and Managing Memory</span></span>  
 <span data-ttu-id="30870-117">Speicherabbilddateien können für mehrere Prozesse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="30870-117">Memory-mapped files can be shared across multiple processes.</span></span> <span data-ttu-id="30870-118">Prozesse können mithilfe eines allgemeinen Namens der gleichen Speicherabbilddatei zugeordnet werden. Dieser allgemeine Name wird von dem Prozess zugewiesen, durch den die Datei erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="30870-118">Processes can map to the same memory-mapped file by using a common name that is assigned by the process that created the file.</span></span>  
  
 <span data-ttu-id="30870-119">Zur Verwendung einer Speicherabbilddatei müssen Sie eine Ansicht der gesamten Speicherabbilddatei oder eines Teils davon erstellen.</span><span class="sxs-lookup"><span data-stu-id="30870-119">To work with a memory-mapped file, you must create a view of the entire memory-mapped file or a part of it.</span></span> <span data-ttu-id="30870-120">Sie können auch mehrere Ansichten für identische Teile der Speicherabbilddatei und dadurch parallelen Arbeitsspeicher erstellen.</span><span class="sxs-lookup"><span data-stu-id="30870-120">You can also create multiple views to the same part of the memory-mapped file, thereby creating concurrent memory.</span></span> <span data-ttu-id="30870-121">Parallele Ansichten müssen aus der gleichen Speicherabbilddatei erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="30870-121">For two views to remain concurrent, they have to be created from the same memory-mapped file.</span></span>  
  
 <span data-ttu-id="30870-122">Mehrere Ansichten können auch erforderlich sein, wenn die Datei größer als der für die Speicherzuordnung verfügbare logische Speicher der Anwendung ist (2 GB auf einem 32-Bit-Computer).</span><span class="sxs-lookup"><span data-stu-id="30870-122">Multiple views may also be necessary if the file is greater than the size of the application's logical memory space available for memory mapping (2 GB on a 32-bit computer).</span></span>  
  
 <span data-ttu-id="30870-123">Zwei Arten von Ansichten werden verwendet: die Streamzugriffsansicht und die Ansicht für direkten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="30870-123">There are two types of views: stream access view and random access view.</span></span> <span data-ttu-id="30870-124">Verwenden Sie für den sequenziellen Zugriff auf eine Datei Streamzugriffsansichten. Dies wird für nicht dauerhaft gespeicherte Dateien und IPC empfohlen.</span><span class="sxs-lookup"><span data-stu-id="30870-124">Use stream access views for sequential access to a file; this is recommended for non-persisted files and IPC.</span></span> <span data-ttu-id="30870-125">Die Ansichten für direkten Zugriff werden beim Arbeiten mit persistent gespeicherten Dateien vorgezogen.</span><span class="sxs-lookup"><span data-stu-id="30870-125">Random access views are preferred for working with persisted files.</span></span>  
  
 <span data-ttu-id="30870-126">Der Zugriff auf im Speicher abgebildete Dateien erfolgt über den Speicher-Manager des Betriebssystems. Die Datei wird daher automatisch in eine Reihe von Seiten partitioniert und nach Bedarf verwendet.</span><span class="sxs-lookup"><span data-stu-id="30870-126">Memory-mapped files are accessed through the operating system's memory manager, so the file is automatically partitioned into a number of pages and accessed as needed.</span></span> <span data-ttu-id="30870-127">Die Speicherverwaltung wird automatisch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="30870-127">You do not have to handle the memory management yourself.</span></span>  
  
 <span data-ttu-id="30870-128">Die folgende Abbildung zeigt, wie für mehrere Prozesse gleichzeitig mehrere überlappende Ansichten derselben Speicherabbilddatei vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="30870-128">The following illustration shows how multiple processes can have multiple and overlapping views to the same memory-mapped file at the same time.</span></span>

 <span data-ttu-id="30870-129">Die folgende Abbildung zeigt mehrere überlappende Ansichten für eine Speicherabbilddatei:</span><span class="sxs-lookup"><span data-stu-id="30870-129">The following image shows multiple and overlapped views to a memory-mapped file:</span></span>  
  
 ![Screenshot mit Ansichten für eine Speicherabbilddatei](./media/memory-mapped-files/memory-map-persist-file.png)  
  
## <a name="programming-with-memory-mapped-files"></a><span data-ttu-id="30870-131">Programmieren mit Speicherabbilddateien</span><span class="sxs-lookup"><span data-stu-id="30870-131">Programming with Memory-Mapped Files</span></span>  
 <span data-ttu-id="30870-132">Die folgende Tabelle enthält Informationen zur Verwendung von Speicherabbilddatei-Objekten und ihren Membern.</span><span class="sxs-lookup"><span data-stu-id="30870-132">The following table provides a guide for using memory-mapped file objects and their members.</span></span>  
  
|<span data-ttu-id="30870-133">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="30870-133">Task</span></span>|<span data-ttu-id="30870-134">Zu verwendende Methoden oder Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="30870-134">Methods or properties to use</span></span>|  
|----------|----------------------------------|  
|<span data-ttu-id="30870-135">Abrufen eines <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>-Objekts, das eine persistent gespeicherte Speicherabbilddatei darstellt, aus einer Datei auf Datenträger</span><span class="sxs-lookup"><span data-stu-id="30870-135">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a persisted memory-mapped file from a file on disk.</span></span>|<span data-ttu-id="30870-136"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="30870-136"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="30870-137">Abrufen eines <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>-Objekts, das eine nicht persistent gespeicherte Speicherabbilddatei darstellt (keiner Datei auf Datenträger zugeordnet)</span><span class="sxs-lookup"><span data-stu-id="30870-137">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a non-persisted memory-mapped file (not associated with a file on disk).</span></span>|<span data-ttu-id="30870-138"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="30870-138"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> method.</span></span><br /><br /> <span data-ttu-id="30870-139">- oder -</span><span class="sxs-lookup"><span data-stu-id="30870-139">- or -</span></span><br /><br /> <span data-ttu-id="30870-140"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="30870-140"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="30870-141">Abrufen eines <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>-Objekts einer vorhandenen Speicherabbilddatei (persistent gespeichert oder nicht persistent gespeichert)</span><span class="sxs-lookup"><span data-stu-id="30870-141">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object of an existing memory-mapped file (either persisted or non-persisted).</span></span>|<span data-ttu-id="30870-142"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="30870-142"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="30870-143">Abrufen eines <xref:System.IO.UnmanagedMemoryStream>-Objekts für eine Ansicht für den sequenziellen Zugriff auf die Speicherabbilddatei</span><span class="sxs-lookup"><span data-stu-id="30870-143">To obtain a <xref:System.IO.UnmanagedMemoryStream> object for a sequentially accessed view to the memory-mapped file.</span></span>|<span data-ttu-id="30870-144"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="30870-144"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="30870-145">Abrufen eines <xref:System.IO.UnmanagedMemoryAccessor>-Objekts für eine Ansicht für den direkten Zugriff auf die Speicherabbilddatei</span><span class="sxs-lookup"><span data-stu-id="30870-145">To obtain a <xref:System.IO.UnmanagedMemoryAccessor> object for a random access view to a memory-mapped fie.</span></span>|<span data-ttu-id="30870-146"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="30870-146"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="30870-147">Abrufen eines <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle>-Objekts, das mit nicht verwaltetem Code verwendet wird</span><span class="sxs-lookup"><span data-stu-id="30870-147">To obtain a <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> object to use with unmanaged code.</span></span>|<span data-ttu-id="30870-148"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="30870-148"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="30870-149">- oder -</span><span class="sxs-lookup"><span data-stu-id="30870-149">- or -</span></span><br /><br /> <span data-ttu-id="30870-150"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="30870-150"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="30870-151">- oder -</span><span class="sxs-lookup"><span data-stu-id="30870-151">- or -</span></span><br /><br /> <span data-ttu-id="30870-152"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="30870-152"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span>|  
|<span data-ttu-id="30870-153">Verzögern der Speicherbelegung, bis eine Ansicht erstellt wird (nur nicht persistent gespeicherte Dateien)</span><span class="sxs-lookup"><span data-stu-id="30870-153">To delay allocating memory until a view is created (non-persisted files only).</span></span><br /><br /> <span data-ttu-id="30870-154">(Verwenden Sie die <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType>-Eigenschaft, um die aktuelle Systemseitengröße zu bestimmen.)</span><span class="sxs-lookup"><span data-stu-id="30870-154">(To determine the current system page size, use the <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> property.)</span></span>|<span data-ttu-id="30870-155">Die <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A>-Methode mit dem <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType>-Wert.</span><span class="sxs-lookup"><span data-stu-id="30870-155"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> method with the <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> value.</span></span><br /><br /> <span data-ttu-id="30870-156">- oder -</span><span class="sxs-lookup"><span data-stu-id="30870-156">- or -</span></span><br /><br /> <span data-ttu-id="30870-157"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>-Methoden mit einer <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions>-Enumeration als Parameter</span><span class="sxs-lookup"><span data-stu-id="30870-157"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods that have a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> enumeration as a parameter.</span></span>|  
  
### <a name="security"></a><span data-ttu-id="30870-158">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="30870-158">Security</span></span>  
 <span data-ttu-id="30870-159">Mit den folgenden Methoden, die eine <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess>-Enumeration als Parameter akzeptieren, können beim Erstellen einer Speicherabbilddatei Zugriffsrechte angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="30870-159">You can apply access rights when you create a memory-mapped file, by using the following methods that take a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> enumeration as a parameter:</span></span>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="30870-160">Sie können mit den <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A>-Methoden, die <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> als Parameter akzeptieren, Zugriffsrechte für das Öffnen einer vorhandenen Speicherabbilddatei angeben.</span><span class="sxs-lookup"><span data-stu-id="30870-160">You can specify access rights for opening an existing memory-mapped file by using the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> methods that take an <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> as a parameter.</span></span>  
  
 <span data-ttu-id="30870-161">Außerdem können Sie ein <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity>-Objekt einschließen, das vordefinierte Zugriffsregeln enthält.</span><span class="sxs-lookup"><span data-stu-id="30870-161">In addition, you can include a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> object that contains predefined access rules.</span></span>  
  
 <span data-ttu-id="30870-162">Verwenden Sie die <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A>-Methode, um neue oder geänderte Zugriffsregeln auf eine Speicherabbilddatei anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="30870-162">To apply new or changed access rules to a memory-mapped file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> method.</span></span> <span data-ttu-id="30870-163">Mit der <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A>-Methode können Zugriffs- oder Überwachungsregeln aus einer vorhandenen Datei abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="30870-163">To retrieve access or audit rules from an existing file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="30870-164">Beispiele</span><span class="sxs-lookup"><span data-stu-id="30870-164">Examples</span></span>  
  
### <a name="persisted-memory-mapped-files"></a><span data-ttu-id="30870-165">Beibehaltene Speicherabbilddateien</span><span class="sxs-lookup"><span data-stu-id="30870-165">Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="30870-166">Die <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A>-Methoden erstellen eine Speicherabbilddatei aus einer vorhandenen Datei auf einem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="30870-166">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> methods create a memory-mapped file from an existing file on disk.</span></span>  
  
 <span data-ttu-id="30870-167">Im folgenden Beispiel wird ein Speicherabbild für einen Teil einer sehr großen Datei erstellt und teilweise bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="30870-167">The following example creates a memory-mapped view of a part of an extremely large file and manipulates a portion of it.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

 <span data-ttu-id="30870-168">Im folgenden Beispiel wird die gleiche Speicherabbilddatei für einen anderen Prozess geöffnet.</span><span class="sxs-lookup"><span data-stu-id="30870-168">The following example opens the same memory-mapped file for another process.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a><span data-ttu-id="30870-169">Nicht beibehaltene Speicherabbilddateien</span><span class="sxs-lookup"><span data-stu-id="30870-169">Non-Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="30870-170">Die <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A>-Methode und die <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>-Methode erstellen eine Speicherabbilddatei, die keiner vorhandenen Datei auf einem Datenträger zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="30870-170">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> and <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods create a memory-mapped file that is not mapped to an existing file on disk.</span></span>  
  
 <span data-ttu-id="30870-171">Das folgende Beispiel umfasst drei separate Prozesse (Konsolenanwendungen), die boolesche Werte in eine Speicherabbilddatei schreiben.</span><span class="sxs-lookup"><span data-stu-id="30870-171">The following example consists of three separate processes (console applications) that write Boolean values to a memory-mapped file.</span></span> <span data-ttu-id="30870-172">Die folgende Sequenz von Aktionen wird ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="30870-172">The following sequence of actions occur:</span></span>  
  
1. <span data-ttu-id="30870-173">`Process A` erstellt die Speicherabbilddatei und schreibt in diese einen Wert.</span><span class="sxs-lookup"><span data-stu-id="30870-173">`Process A` creates the memory-mapped file and writes a value to it.</span></span>  
  
2. <span data-ttu-id="30870-174">`Process B` erstellt die Speicherabbilddatei und schreibt in diese einen Wert.</span><span class="sxs-lookup"><span data-stu-id="30870-174">`Process B` opens the memory-mapped file and writes a value to it.</span></span>  
  
3. <span data-ttu-id="30870-175">`Process C` erstellt die Speicherabbilddatei und schreibt in diese einen Wert.</span><span class="sxs-lookup"><span data-stu-id="30870-175">`Process C` opens the memory-mapped file and writes a value to it.</span></span>  
  
4. <span data-ttu-id="30870-176">`Process A` liest die Werte in der Speicherabbilddatei und zeigt diese an.</span><span class="sxs-lookup"><span data-stu-id="30870-176">`Process A` reads and displays the values from the memory-mapped file.</span></span>  
  
5. <span data-ttu-id="30870-177">Nachdem die Bearbeitung der Speicherabbilddatei durch `Process A` abgeschlossen ist, wird die Datei sofort von der Garbage Collection freigegeben.</span><span class="sxs-lookup"><span data-stu-id="30870-177">After `Process A` is finished with the memory-mapped file, the file is immediately reclaimed by garbage collection.</span></span>  
  
 <span data-ttu-id="30870-178">Gehen Sie folgendermaßen vor, um dieses Beispiel auszuführen:</span><span class="sxs-lookup"><span data-stu-id="30870-178">To run this example, do the following:</span></span>  
  
1. <span data-ttu-id="30870-179">Kompilieren Sie die Anwendungen, und öffnen Sie drei Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="30870-179">Compile the applications and open three Command Prompt windows.</span></span>  
  
2. <span data-ttu-id="30870-180">Führen Sie `Process A` im ersten Eingabeaufforderungsfenster aus.</span><span class="sxs-lookup"><span data-stu-id="30870-180">In the first Command Prompt window, run `Process A`.</span></span>  
  
3. <span data-ttu-id="30870-181">Führen Sie `Process B` im zweiten Eingabeaufforderungsfenster aus.</span><span class="sxs-lookup"><span data-stu-id="30870-181">In the second Command Prompt window, run `Process B`.</span></span>  
  
4. <span data-ttu-id="30870-182">Kehren Sie zu `Process A` zurück, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="30870-182">Return to `Process A` and press ENTER.</span></span>  
  
5. <span data-ttu-id="30870-183">Führen Sie `Process C` im dritten Eingabeaufforderungsfenster aus.</span><span class="sxs-lookup"><span data-stu-id="30870-183">In the third Command Prompt window, run `Process C`.</span></span>  
  
6. <span data-ttu-id="30870-184">Kehren Sie zu `Process A` zurück, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="30870-184">Return to `Process A` and press ENTER.</span></span>  
  
 <span data-ttu-id="30870-185">Die Ausgabe von `Process A` lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="30870-185">The output of `Process A` is as follows:</span></span>  
  
```console  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 <span data-ttu-id="30870-186">**Prozess A**</span><span class="sxs-lookup"><span data-stu-id="30870-186">**Process A**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 <span data-ttu-id="30870-187">**Prozess B**</span><span class="sxs-lookup"><span data-stu-id="30870-187">**Process B**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 <span data-ttu-id="30870-188">**Prozess C**</span><span class="sxs-lookup"><span data-stu-id="30870-188">**Process C**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="30870-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30870-189">See also</span></span>

- [<span data-ttu-id="30870-190">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="30870-190">File and Stream I/O</span></span>](index.md)
