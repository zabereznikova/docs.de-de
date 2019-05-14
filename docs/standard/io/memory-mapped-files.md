---
title: Speicherabbilddateien
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- memory-mapped files
- inter-process communication
ms.assetid: a483d1b5-64aa-45b6-86ef-11b859f7f02e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd1ced48847739318f22ec77b17a83a36fd36ee0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647766"
---
# <a name="memory-mapped-files"></a><span data-ttu-id="8f03b-102">Speicherabbilddateien</span><span class="sxs-lookup"><span data-stu-id="8f03b-102">Memory-Mapped Files</span></span>
<span data-ttu-id="8f03b-103">Eine Speicherabbilddatei enthält den Inhalt einer Datei im virtuellen Speicher.</span><span class="sxs-lookup"><span data-stu-id="8f03b-103">A memory-mapped file contains the contents of a file in virtual memory.</span></span> <span data-ttu-id="8f03b-104">Diese Zuordnung zwischen einer Datei und Speicherplatz ermöglicht es einer Anwendung mit mehreren Prozessen, die Datei durch direktes Lesen und Schreiben im Arbeitsspeicher zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8f03b-104">This mapping between a file and memory space enables an application, including multiple processes, to modify the file by reading and writing directly to the memory.</span></span> <span data-ttu-id="8f03b-105">Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] können Sie verwalteten Code verwenden, um auf die gleiche Weise auf Speicherabbilddateien zuzugreifen wie native Windows-Funktionen. Dies wird unter [Managing Memory-Mapped Files](https://docs.microsoft.com/previous-versions/ms810613(v=msdn.10)) (Verwalten von Speicherabbilddateien) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f03b-105">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use managed code to access memory-mapped files in the same way that native Windows functions access memory-mapped files, as described in [Managing Memory-Mapped Files](https://docs.microsoft.com/previous-versions/ms810613(v=msdn.10)).</span></span>  
  
 <span data-ttu-id="8f03b-106">Es gibt zwei Arten von Speicherabbilddateien:</span><span class="sxs-lookup"><span data-stu-id="8f03b-106">There are two types of memory-mapped files:</span></span>  
  
- <span data-ttu-id="8f03b-107">Beibehaltene Speicherabbilddateien</span><span class="sxs-lookup"><span data-stu-id="8f03b-107">Persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="8f03b-108">Persistent gespeicherte Dateien sind Speicherabbilddateien, die einer Quelldatei auf einem Datenträger zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8f03b-108">Persisted files are memory-mapped files that are associated with a source file on a disk.</span></span> <span data-ttu-id="8f03b-109">Wenn der letzte Prozess die Verwendung der Datei beendet, werden die Daten in der Quelldatei auf dem Datenträger gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8f03b-109">When the last process has finished working with the file, the data is saved to the source file on the disk.</span></span> <span data-ttu-id="8f03b-110">Diese Speicherabbilddateien eignen sich für extrem große Quelldateien.</span><span class="sxs-lookup"><span data-stu-id="8f03b-110">These memory-mapped files are suitable for working with extremely large source files.</span></span>  
  
- <span data-ttu-id="8f03b-111">Nicht beibehaltene Speicherabbilddateien</span><span class="sxs-lookup"><span data-stu-id="8f03b-111">Non-persisted memory-mapped files</span></span>  
  
     <span data-ttu-id="8f03b-112">Nicht persistent gespeicherte Dateien sind Speicherabbilddateien, die keiner Datei auf einem Datenträger zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8f03b-112">Non-persisted files are memory-mapped files that are not associated with a file on a disk.</span></span> <span data-ttu-id="8f03b-113">Wenn der letzte Prozess die Verwendung der Datei beendet, gehen die Daten verloren, und die Datei wird von der Garbage Collection freigegeben.</span><span class="sxs-lookup"><span data-stu-id="8f03b-113">When the last process has finished working with the file, the data is lost and the file is reclaimed by garbage collection.</span></span> <span data-ttu-id="8f03b-114">Diese Dateien eignen sich zum Erstellen von freigegebenen Speicherbereichen für die prozessübergreifende Kommunikation (IPC).</span><span class="sxs-lookup"><span data-stu-id="8f03b-114">These files are suitable for creating shared memory for inter-process communications (IPC).</span></span>  
  
## <a name="processes-views-and-managing-memory"></a><span data-ttu-id="8f03b-115">Prozesse, Ansichten und Verwalten des Arbeitsspeichers</span><span class="sxs-lookup"><span data-stu-id="8f03b-115">Processes, Views, and Managing Memory</span></span>  
 <span data-ttu-id="8f03b-116">Speicherabbilddateien können für mehrere Prozesse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f03b-116">Memory-mapped files can be shared across multiple processes.</span></span> <span data-ttu-id="8f03b-117">Prozesse können mithilfe eines allgemeinen Namens der gleichen Speicherabbilddatei zugeordnet werden. Dieser allgemeine Name wird von dem Prozess zugewiesen, durch den die Datei erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="8f03b-117">Processes can map to the same memory-mapped file by using a common name that is assigned by the process that created the file.</span></span>  
  
 <span data-ttu-id="8f03b-118">Zur Verwendung einer Speicherabbilddatei müssen Sie eine Ansicht der gesamten Speicherabbilddatei oder eines Teils davon erstellen.</span><span class="sxs-lookup"><span data-stu-id="8f03b-118">To work with a memory-mapped file, you must create a view of the entire memory-mapped file or a part of it.</span></span> <span data-ttu-id="8f03b-119">Sie können auch mehrere Ansichten für identische Teile der Speicherabbilddatei und dadurch parallelen Arbeitsspeicher erstellen.</span><span class="sxs-lookup"><span data-stu-id="8f03b-119">You can also create multiple views to the same part of the memory-mapped file, thereby creating concurrent memory.</span></span> <span data-ttu-id="8f03b-120">Parallele Ansichten müssen aus der gleichen Speicherabbilddatei erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8f03b-120">For two views to remain concurrent, they have to be created from the same memory-mapped file.</span></span>  
  
 <span data-ttu-id="8f03b-121">Mehrere Ansichten können auch erforderlich sein, wenn die Datei größer als der für die Speicherzuordnung verfügbare logische Speicher der Anwendung ist (2 GB auf einem 32-Bit-Computer).</span><span class="sxs-lookup"><span data-stu-id="8f03b-121">Multiple views may also be necessary if the file is greater than the size of the application’s logical memory space available for memory mapping (2 GB on a 32-bit computer).</span></span>  
  
 <span data-ttu-id="8f03b-122">Zwei Arten von Ansichten werden verwendet: die Streamzugriffsansicht und die Ansicht für direkten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="8f03b-122">There are two types of views: stream access view and random access view.</span></span> <span data-ttu-id="8f03b-123">Verwenden Sie für den sequenziellen Zugriff auf eine Datei Streamzugriffsansichten. Dies wird für nicht dauerhaft gespeicherte Dateien und IPC empfohlen.</span><span class="sxs-lookup"><span data-stu-id="8f03b-123">Use stream access views for sequential access to a file; this is recommended for non-persisted files and IPC.</span></span> <span data-ttu-id="8f03b-124">Die Ansichten für direkten Zugriff werden beim Arbeiten mit persistent gespeicherten Dateien vorgezogen.</span><span class="sxs-lookup"><span data-stu-id="8f03b-124">Random access views are preferred for working with persisted files.</span></span>  
  
 <span data-ttu-id="8f03b-125">Der Zugriff auf Speicherabbilddateien erfolgt über den Speicher-Manager des Betriebssystems. Die Datei wird daher automatisch in eine Reihe von Seiten partitioniert und nach Bedarf verwendet.</span><span class="sxs-lookup"><span data-stu-id="8f03b-125">Memory-mapped files are accessed through the operating system’s memory manager, so the file is automatically partitioned into a number of pages and accessed as needed.</span></span> <span data-ttu-id="8f03b-126">Die Speicherverwaltung wird automatisch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8f03b-126">You do not have to handle the memory management yourself.</span></span>  
  
 <span data-ttu-id="8f03b-127">Die folgende Abbildung zeigt, wie für mehrere Prozesse gleichzeitig mehrere überlappende Ansichten derselben Speicherabbilddatei vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="8f03b-127">The following illustration shows how multiple processes can have multiple and overlapping views to the same memory-mapped file at the same time.</span></span>

 <span data-ttu-id="8f03b-128">Die folgende Abbildung zeigt mehrere überlappende Ansichten für eine Speicherabbilddatei:</span><span class="sxs-lookup"><span data-stu-id="8f03b-128">The following image shows multiple and overlapped views to a memory-mapped file:</span></span>  
  
 ![Screenshot mit Ansichten für eine Speicherabbilddatei](./media/memory-mapped-files/memory-map-persist-file.png)  
  
## <a name="programming-with-memory-mapped-files"></a><span data-ttu-id="8f03b-130">Programmieren mit Speicherabbilddateien</span><span class="sxs-lookup"><span data-stu-id="8f03b-130">Programming with Memory-Mapped Files</span></span>  
 <span data-ttu-id="8f03b-131">Die folgende Tabelle enthält Informationen zur Verwendung von Speicherabbilddatei-Objekten und ihren Membern.</span><span class="sxs-lookup"><span data-stu-id="8f03b-131">The following table provides a guide for using memory-mapped file objects and their members.</span></span>  
  
|<span data-ttu-id="8f03b-132">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="8f03b-132">Task</span></span>|<span data-ttu-id="8f03b-133">Zu verwendende Methoden oder Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8f03b-133">Methods or properties to use</span></span>|  
|----------|----------------------------------|  
|<span data-ttu-id="8f03b-134">Abrufen eines <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>-Objekts, das eine persistent gespeicherte Speicherabbilddatei darstellt, aus einer Datei auf Datenträger</span><span class="sxs-lookup"><span data-stu-id="8f03b-134">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a persisted memory-mapped file from a file on disk.</span></span>|<span data-ttu-id="8f03b-135"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="8f03b-135"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="8f03b-136">Abrufen eines <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>-Objekts, das eine nicht persistent gespeicherte Speicherabbilddatei darstellt (keiner Datei auf Datenträger zugeordnet)</span><span class="sxs-lookup"><span data-stu-id="8f03b-136">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object that represents a non-persisted memory-mapped file (not associated with a file on disk).</span></span>|<span data-ttu-id="8f03b-137"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="8f03b-137"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType> method.</span></span><br /><br /> <span data-ttu-id="8f03b-138">- oder -</span><span class="sxs-lookup"><span data-stu-id="8f03b-138">- or -</span></span><br /><br /> <span data-ttu-id="8f03b-139"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="8f03b-139"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="8f03b-140">Abrufen eines <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>-Objekts einer vorhandenen Speicherabbilddatei (persistent gespeichert oder nicht persistent gespeichert)</span><span class="sxs-lookup"><span data-stu-id="8f03b-140">To obtain a <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> object of an existing memory-mapped file (either persisted or non-persisted).</span></span>|<span data-ttu-id="8f03b-141"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="8f03b-141"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="8f03b-142">Abrufen eines <xref:System.IO.UnmanagedMemoryStream>-Objekts für eine Ansicht für den sequenziellen Zugriff auf die Speicherabbilddatei</span><span class="sxs-lookup"><span data-stu-id="8f03b-142">To obtain a <xref:System.IO.UnmanagedMemoryStream> object for a sequentially accessed view to the memory-mapped file.</span></span>|<span data-ttu-id="8f03b-143"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="8f03b-143"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewStream%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="8f03b-144">Abrufen eines <xref:System.IO.UnmanagedMemoryAccessor>-Objekts für eine Ansicht für den direkten Zugriff auf die Speicherabbilddatei</span><span class="sxs-lookup"><span data-stu-id="8f03b-144">To obtain a <xref:System.IO.UnmanagedMemoryAccessor> object for a random access view to a memory-mapped fie.</span></span>|<span data-ttu-id="8f03b-145"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="8f03b-145"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateViewAccessor%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="8f03b-146">Abrufen eines <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle>-Objekts, das mit nicht verwaltetem Code verwendet wird</span><span class="sxs-lookup"><span data-stu-id="8f03b-146">To obtain a <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> object to use with unmanaged code.</span></span>|<span data-ttu-id="8f03b-147"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8f03b-147"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SafeMemoryMappedFileHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="8f03b-148">- oder -</span><span class="sxs-lookup"><span data-stu-id="8f03b-148">- or -</span></span><br /><br /> <span data-ttu-id="8f03b-149"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8f03b-149"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewAccessor.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span><br /><br /> <span data-ttu-id="8f03b-150">- oder -</span><span class="sxs-lookup"><span data-stu-id="8f03b-150">- or -</span></span><br /><br /> <span data-ttu-id="8f03b-151"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8f03b-151"><xref:System.IO.MemoryMappedFiles.MemoryMappedViewStream.SafeMemoryMappedViewHandle%2A?displayProperty=nameWithType> property.</span></span>|  
|<span data-ttu-id="8f03b-152">Verzögern der Speicherbelegung, bis eine Ansicht erstellt wird (nur nicht persistent gespeicherte Dateien)</span><span class="sxs-lookup"><span data-stu-id="8f03b-152">To delay allocating memory until a view is created (non-persisted files only).</span></span><br /><br /> <span data-ttu-id="8f03b-153">(Verwenden Sie die <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType>-Eigenschaft, um die aktuelle Systemseitengröße zu bestimmen.)</span><span class="sxs-lookup"><span data-stu-id="8f03b-153">(To determine the current system page size, use the <xref:System.Environment.SystemPageSize%2A?displayProperty=nameWithType> property.)</span></span>|<span data-ttu-id="8f03b-154">Die <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A>-Methode mit dem <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType>-Wert.</span><span class="sxs-lookup"><span data-stu-id="8f03b-154"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> method with the <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions.DelayAllocatePages?displayProperty=nameWithType> value.</span></span><br /><br /> <span data-ttu-id="8f03b-155">- oder -</span><span class="sxs-lookup"><span data-stu-id="8f03b-155">- or -</span></span><br /><br /> <span data-ttu-id="8f03b-156"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>-Methoden mit einer <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions>-Enumeration als Parameter</span><span class="sxs-lookup"><span data-stu-id="8f03b-156"><xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods that have a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileOptions> enumeration as a parameter.</span></span>|  
  
### <a name="security"></a><span data-ttu-id="8f03b-157">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8f03b-157">Security</span></span>  
 <span data-ttu-id="8f03b-158">Mit den folgenden Methoden, die eine <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess>-Enumeration als Parameter akzeptieren, können beim Erstellen einer Speicherabbilddatei Zugriffsrechte angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="8f03b-158">You can apply access rights when you create a memory-mapped file, by using the following methods that take a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileAccess> enumeration as a parameter:</span></span>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A?displayProperty=nameWithType>  
  
- <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="8f03b-159">Sie können mit den <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A>-Methoden, die <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> als Parameter akzeptieren, Zugriffsrechte für das Öffnen einer vorhandenen Speicherabbilddatei angeben.</span><span class="sxs-lookup"><span data-stu-id="8f03b-159">You can specify access rights for opening an existing memory-mapped file by using the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.OpenExisting%2A> methods that take an <xref:System.IO.MemoryMappedFiles.MemoryMappedFileRights> as a parameter.</span></span>  
  
 <span data-ttu-id="8f03b-160">Außerdem können Sie ein <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity>-Objekt einschließen, das vordefinierte Zugriffsregeln enthält.</span><span class="sxs-lookup"><span data-stu-id="8f03b-160">In addition, you can include a <xref:System.IO.MemoryMappedFiles.MemoryMappedFileSecurity> object that contains predefined access rules.</span></span>  
  
 <span data-ttu-id="8f03b-161">Verwenden Sie die <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A>-Methode, um neue oder geänderte Zugriffsregeln auf eine Speicherabbilddatei anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="8f03b-161">To apply new or changed access rules to a memory-mapped file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.SetAccessControl%2A> method.</span></span> <span data-ttu-id="8f03b-162">Mit der <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A>-Methode können Zugriffs- oder Überwachungsregeln aus einer vorhandenen Datei abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8f03b-162">To retrieve access or audit rules from an existing file, use the <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.GetAccessControl%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8f03b-163">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8f03b-163">Examples</span></span>  
  
### <a name="persisted-memory-mapped-files"></a><span data-ttu-id="8f03b-164">Beibehaltene Speicherabbilddateien</span><span class="sxs-lookup"><span data-stu-id="8f03b-164">Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="8f03b-165">Die <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A>-Methoden erstellen eine Speicherabbilddatei aus einer vorhandenen Datei auf einem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="8f03b-165">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateFromFile%2A> methods create a memory-mapped file from an existing file on disk.</span></span>  
  
 <span data-ttu-id="8f03b-166">Im folgenden Beispiel wird ein Speicherabbild für einen Teil einer sehr großen Datei erstellt und teilweise bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="8f03b-166">The following example creates a memory-mapped view of a part of an extremely large file and manipulates a portion of it.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.CreateFromFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.createfromfile/vb/program.vb#1)]  
  
 <span data-ttu-id="8f03b-167">Im folgenden Beispiel wird die gleiche Speicherabbilddatei für einen anderen Prozess geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8f03b-167">The following example opens the same memory-mapped file for another process.</span></span>  
  
 [!code-csharp[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/cs/program.cs#1)]
 [!code-vb[MemoryMappedFiles.MemoryMappedFile.OpenExisting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/memorymappedfiles.memorymappedfile.openexisting/vb/program.vb#1)]  
  
### <a name="non-persisted-memory-mapped-files"></a><span data-ttu-id="8f03b-168">Nicht beibehaltene Speicherabbilddateien</span><span class="sxs-lookup"><span data-stu-id="8f03b-168">Non-Persisted Memory-Mapped Files</span></span>  
 <span data-ttu-id="8f03b-169">Die <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A>-Methode und die <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A>-Methode erstellen eine Speicherabbilddatei, die keiner vorhandenen Datei auf einem Datenträger zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8f03b-169">The <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateNew%2A> and <xref:System.IO.MemoryMappedFiles.MemoryMappedFile.CreateOrOpen%2A> methods create a memory-mapped file that is not mapped to an existing file on disk.</span></span>  
  
 <span data-ttu-id="8f03b-170">Das folgende Beispiel umfasst drei separate Prozesse (Konsolenanwendungen), die boolesche Werte in eine Speicherabbilddatei schreiben.</span><span class="sxs-lookup"><span data-stu-id="8f03b-170">The following example consists of three separate processes (console applications) that write Boolean values to a memory-mapped file.</span></span> <span data-ttu-id="8f03b-171">Die folgende Sequenz von Aktionen wird ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="8f03b-171">The following sequence of actions occur:</span></span>  
  
1. <span data-ttu-id="8f03b-172">`Process A` erstellt die Speicherabbilddatei und schreibt in diese einen Wert.</span><span class="sxs-lookup"><span data-stu-id="8f03b-172">`Process A` creates the memory-mapped file and writes a value to it.</span></span>  
  
2. <span data-ttu-id="8f03b-173">`Process B` erstellt die Speicherabbilddatei und schreibt in diese einen Wert.</span><span class="sxs-lookup"><span data-stu-id="8f03b-173">`Process B` opens the memory-mapped file and writes a value to it.</span></span>  
  
3. <span data-ttu-id="8f03b-174">`Process C` erstellt die Speicherabbilddatei und schreibt in diese einen Wert.</span><span class="sxs-lookup"><span data-stu-id="8f03b-174">`Process C` opens the memory-mapped file and writes a value to it.</span></span>  
  
4. <span data-ttu-id="8f03b-175">`Process A` liest die Werte in der Speicherabbilddatei und zeigt diese an.</span><span class="sxs-lookup"><span data-stu-id="8f03b-175">`Process A` reads and displays the values from the memory-mapped file.</span></span>  
  
5. <span data-ttu-id="8f03b-176">Nachdem die Bearbeitung der Speicherabbilddatei durch `Process A` abgeschlossen ist, wird die Datei sofort von der Garbage Collection freigegeben.</span><span class="sxs-lookup"><span data-stu-id="8f03b-176">After `Process A` is finished with the memory-mapped file, the file is immediately reclaimed by garbage collection.</span></span>  
  
 <span data-ttu-id="8f03b-177">Gehen Sie folgendermaßen vor, um dieses Beispiel auszuführen:</span><span class="sxs-lookup"><span data-stu-id="8f03b-177">To run this example, do the following:</span></span>  
  
1. <span data-ttu-id="8f03b-178">Kompilieren Sie die Anwendungen, und öffnen Sie drei Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="8f03b-178">Compile the applications and open three Command Prompt windows.</span></span>  
  
2. <span data-ttu-id="8f03b-179">Führen Sie `Process A` im ersten Eingabeaufforderungsfenster aus.</span><span class="sxs-lookup"><span data-stu-id="8f03b-179">In the first Command Prompt window, run `Process A`.</span></span>  
  
3. <span data-ttu-id="8f03b-180">Führen Sie `Process B` im zweiten Eingabeaufforderungsfenster aus.</span><span class="sxs-lookup"><span data-stu-id="8f03b-180">In the second Command Prompt window, run `Process B`.</span></span>  
  
4. <span data-ttu-id="8f03b-181">Kehren Sie zu `Process A` zurück, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="8f03b-181">Return to `Process A` and press ENTER.</span></span>  
  
5. <span data-ttu-id="8f03b-182">Führen Sie `Process C` im dritten Eingabeaufforderungsfenster aus.</span><span class="sxs-lookup"><span data-stu-id="8f03b-182">In the third Command Prompt window, run `Process C`.</span></span>  
  
6. <span data-ttu-id="8f03b-183">Kehren Sie zu `Process A` zurück, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="8f03b-183">Return to `Process A` and press ENTER.</span></span>  
  
 <span data-ttu-id="8f03b-184">Die Ausgabe von `Process A` lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8f03b-184">The output of `Process A` is as follows:</span></span>  
  
```  
Start Process B and press ENTER to continue.  
Start Process C and press ENTER to continue.  
Process A says: True  
Process B says: False  
Process C says: True  
```  
  
 <span data-ttu-id="8f03b-185">**Prozess A**</span><span class="sxs-lookup"><span data-stu-id="8f03b-185">**Process A**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_X#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_x/vb/program.vb#1)]  
  
 <span data-ttu-id="8f03b-186">**Prozess B**</span><span class="sxs-lookup"><span data-stu-id="8f03b-186">**Process B**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_A#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_a/vb/program.vb#1)]  
  
 <span data-ttu-id="8f03b-187">**Prozess C**</span><span class="sxs-lookup"><span data-stu-id="8f03b-187">**Process C**</span></span>  
  
 [!code-csharp[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/cs/program.cs#1)]
 [!code-vb[System.IO.MemoryMappedFiles_IPC_B#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.memorymappedfiles_ipc_b/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8f03b-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f03b-188">See also</span></span>

- [<span data-ttu-id="8f03b-189">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="8f03b-189">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
