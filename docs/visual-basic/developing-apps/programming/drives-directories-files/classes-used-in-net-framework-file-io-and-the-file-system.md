---
title: "Für Datei-E/A-Vorgänge und die Arbeit mit dem Dateisystem in .NET Framework verwendete Klassen (Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- file I/O classes
ms.assetid: 4a5ca924-eea8-4a95-a5f0-6ac10de276a3
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a87d2e6f87b92b5f66706095d3f485c080008e0f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="classes-used-in-net-framework-file-io-and-the-file-system-visual-basic"></a><span data-ttu-id="49998-102">Für Datei-E/A-Vorgänge und die Arbeit mit dem Dateisystem in .NET Framework verwendete Klassen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49998-102">Classes Used in .NET Framework File I/O and the File System (Visual Basic)</span></span>
<span data-ttu-id="49998-103">In den folgenden Tabellen sind die Klassen aufgelistet, die häufig für .NET Framework-Datei-E/A verwendet werden, kategorisiert in Datei-E/A-Klassen, Klassen zum Erstellen von Streams und Klassen zum Lesen und Schreiben in Streams.</span><span class="sxs-lookup"><span data-stu-id="49998-103">The following tables list the classes commonly used for .NET Framework file I/O, categorized into file I/O classes, classes used for creating streams, and classes used to read and write to streams.</span></span>  
  
 <span data-ttu-id="49998-104">Für das Betreten der [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)]-Dokumentation und eine umfassendere Auflistung siehe [Übersicht über die Klassenbibliothek](https://msdn.microsoft.com/library/hfa3fa08).</span><span class="sxs-lookup"><span data-stu-id="49998-104">To enter the [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] documentation and find a more comprehensive listing, see [Class Library Overview](https://msdn.microsoft.com/library/hfa3fa08).</span></span>  
  
## <a name="basic-io-classes-for-files-drives-and-directories"></a><span data-ttu-id="49998-105">Grundlegende E/A-Klassen für Dateien, Laufwerke und Verzeichnisse</span><span class="sxs-lookup"><span data-stu-id="49998-105">Basic I/O Classes for Files, Drives, and Directories</span></span>  
 <span data-ttu-id="49998-106">In der folgenden Tabelle werden die wichtigsten Klassen aufgeführt und beschrieben, die für Datei-E/A verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="49998-106">The following table lists and describes the main classes used for file I/O.</span></span>  
  
|<span data-ttu-id="49998-107">Klasse</span><span class="sxs-lookup"><span data-stu-id="49998-107">Class</span></span>|<span data-ttu-id="49998-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49998-108">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.IO.Directory?displayProperty=fullName>|<span data-ttu-id="49998-109">Stellt statische Methoden zum Erstellen, Verschieben und Auflisten über Verzeichnisse und Unterverzeichnisse hinweg zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="49998-109">Provides static methods for creating, moving, and enumerating through directories and subdirectories.</span></span>|  
|<xref:System.IO.DirectoryInfo?displayProperty=fullName>|<span data-ttu-id="49998-110">Stellt Instanzmethoden zum Erstellen, Verschieben und Auflisten über Verzeichnisse und Unterverzeichnisse hinweg zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="49998-110">Provides instance methods for creating, moving, and enumerating through directories and subdirectories.</span></span>|  
|<xref:System.IO.DriveInfo?displayProperty=fullName>|<span data-ttu-id="49998-111">Stellt Instanzmethoden zum Erstellen, Verschieben und Auflisten über Laufwerke hinweg zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="49998-111">Provides instance methods for creating, moving, and enumerating through drives.</span></span>|  
|<xref:System.IO.File?displayProperty=fullName>|<span data-ttu-id="49998-112">Stellt statische Methoden zum Erstellen, Kopieren, Löschen, Verschieben und Öffnen von Dateien zur Verfügung und unterstützt das Erstellen eines `FileStream`.</span><span class="sxs-lookup"><span data-stu-id="49998-112">Provides static methods for creating, copying, deleting, moving, and opening files, and aids in the creation of a `FileStream`.</span></span>|  
|<xref:System.IO.FileAccess?displayProperty=fullName>|<span data-ttu-id="49998-113">Definiert Konstanten für den Lese-, Schreib- oder Lese-/Schreibzugriff auf eine Datei.</span><span class="sxs-lookup"><span data-stu-id="49998-113">Defines constants for read, write, or read/write access to a file.</span></span>|  
|<xref:System.IO.FileAttributes?displayProperty=fullName>|<span data-ttu-id="49998-114">Stellt Attribute für Dateien und Verzeichnisse wie `Archive`, `Hidden` und `ReadOnly` bereit.</span><span class="sxs-lookup"><span data-stu-id="49998-114">Provides attributes for files and directories such as `Archive`, `Hidden`, and `ReadOnly`.</span></span>|  
|<xref:System.IO.FileInfo?displayProperty=fullName>|<span data-ttu-id="49998-115">Stellt statische Methoden zum Erstellen, Kopieren, Löschen, Verschieben und Öffnen von Dateien zur Verfügung und unterstützt das Erstellen eines `FileStream`.</span><span class="sxs-lookup"><span data-stu-id="49998-115">Provides static methods for creating, copying, deleting, moving, and opening files, and aids in the creation of a `FileStream`.</span></span>|  
|<xref:System.IO.FileMode?displayProperty=fullName>|<span data-ttu-id="49998-116">Steuert, wie eine Datei geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="49998-116">Controls how a file is opened.</span></span> <span data-ttu-id="49998-117">Dieser Parameter wird in vielen der Konstruktoren für `FileStream` und `IsolatedStorageFileStream` sowie für die `Open`-Methoden von <xref:System.IO.File> und <xref:System.IO.FileInfo> angegeben.</span><span class="sxs-lookup"><span data-stu-id="49998-117">This parameter is specified in many of the constructors for `FileStream` and `IsolatedStorageFileStream`, and for the `Open` methods of <xref:System.IO.File> and <xref:System.IO.FileInfo>.</span></span>|  
|<xref:System.IO.FileShare?displayProperty=fullName>|<span data-ttu-id="49998-118">Definiert Konstanten für das Steuern des Zugriffstyps von anderen Dateistreams auf dieselbe Datei.</span><span class="sxs-lookup"><span data-stu-id="49998-118">Defines constants for controlling the type of access other file streams can have to the same file.</span></span>|  
|<xref:System.IO.Path?displayProperty=fullName>|<span data-ttu-id="49998-119">Stellt Methoden und Eigenschaften für die Verarbeitung von Verzeichniszeichenfolgen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="49998-119">Provides methods and properties for processing directory strings.</span></span>|  
|<xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>|<span data-ttu-id="49998-120">Steuert den Zugriff von Dateien und Ordnern durch Definieren der Berechtigungen <xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> und <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>.</span><span class="sxs-lookup"><span data-stu-id="49998-120">Controls the access of files and folders by defining <xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> and <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> permissions.</span></span>|  
  
## <a name="classes-used-to-create-streams"></a><span data-ttu-id="49998-121">Klassen zum Erstellen von Streams</span><span class="sxs-lookup"><span data-stu-id="49998-121">Classes Used to Create Streams</span></span>  
 <span data-ttu-id="49998-122">In der folgenden Tabelle werden die wichtigsten Klassen aufgeführt und beschrieben, die zum Erstellen von Streams verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="49998-122">The following table lists and describes the main classes used to create streams.</span></span>  
  
|<span data-ttu-id="49998-123">Klasse</span><span class="sxs-lookup"><span data-stu-id="49998-123">Class</span></span>|<span data-ttu-id="49998-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49998-124">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.IO.BufferedStream?displayProperty=fullName>|<span data-ttu-id="49998-125">Fügt eine Pufferebene zu Lese- und Schreibvorgängen auf einem anderen Stream hinzu.</span><span class="sxs-lookup"><span data-stu-id="49998-125">Adds a buffering layer to read and write operations on another stream.</span></span>|  
|<xref:System.IO.FileStream?displayProperty=fullName>|<span data-ttu-id="49998-126">Unterstützt den zufälligen Zugriff auf Dateien über die <xref:System.IO.FileStream.Seek%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="49998-126">Supports random access to files through its <xref:System.IO.FileStream.Seek%2A> method.</span></span> <span data-ttu-id="49998-127"><xref:System.IO.FileStream> öffnet Dateien standardmäßig synchron, unterstützt aber auch den asynchronen Vorgang.</span><span class="sxs-lookup"><span data-stu-id="49998-127"><xref:System.IO.FileStream> opens files synchronously by default but also supports asynchronous operation.</span></span>|  
|<xref:System.IO.MemoryStream?displayProperty=fullName>|<span data-ttu-id="49998-128">Erstellt einen Stream, der den Arbeitsspeicher anstatt einer Datei als Sicherungsspeicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="49998-128">Creates a stream whose backing store is memory, rather than a file.</span></span>|  
|<xref:System.Net.Sockets.NetworkStream?displayProperty=fullName>|<span data-ttu-id="49998-129">Stellt den zugrunde liegenden Datenstrom für den Netzwerkzugriff bereit.</span><span class="sxs-lookup"><span data-stu-id="49998-129">Provides the underlying stream of data for network access.</span></span>|  
|<xref:System.Security.Cryptography.CryptoStream?displayProperty=fullName>|<span data-ttu-id="49998-130">Definiert einen Stream, der Datenstreams mit kryptografischen Transformationen verknüpft.</span><span class="sxs-lookup"><span data-stu-id="49998-130">Defines a stream that links data streams to cryptographic transformations.</span></span>|  
  
## <a name="classes-used-to-read-from-and-write-to-streams"></a><span data-ttu-id="49998-131">Klassen, die zum Lesen aus und Schreiben an Streams verwendet werden</span><span class="sxs-lookup"><span data-stu-id="49998-131">Classes Used to Read from and Write to Streams</span></span>  
 <span data-ttu-id="49998-132">Die folgende Tabelle zeigt die spezifischen Klassen, die zum Lesen aus und Schreiben an Dateien mit Streams verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="49998-132">The following table shows the specific classes used for reading from and writing to files with streams.</span></span>  
  
|<span data-ttu-id="49998-133">**Klasse**</span><span class="sxs-lookup"><span data-stu-id="49998-133">**Class**</span></span>|<span data-ttu-id="49998-134">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="49998-134">**Description**</span></span>|  
|---------------|---------------------|  
|<xref:System.IO.BinaryReader?displayProperty=fullName>|<span data-ttu-id="49998-135">Liest codierte Zeichenfolgen und primitive Datentypen aus einem <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="49998-135">Reads encoded strings and primitive data types from a <xref:System.IO.FileStream>.</span></span>|  
|<xref:System.IO.BinaryWriter?displayProperty=fullName>|<span data-ttu-id="49998-136">Schreibt codierte Zeichenfolgen und primitive Datentypen in einen <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="49998-136">Writes encoded strings and primitive data types to a <xref:System.IO.FileStream>.</span></span>|  
|<xref:System.IO.StreamReader?displayProperty=fullName>|<span data-ttu-id="49998-137">Liest Zeichen aus einem <xref:System.IO.FileStream>, wobei <xref:System.IO.StreamReader.CurrentEncoding%2A> zum Konvertieren von Zeichen in und aus Bytes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="49998-137">Reads characters from a <xref:System.IO.FileStream>, using <xref:System.IO.StreamReader.CurrentEncoding%2A> to convert characters to and from bytes.</span></span> <span data-ttu-id="49998-138"><xref:System.IO.StreamReader> verfügt über einen Konstruktor, der basierend auf dem Vorhandensein einer <xref:System.IO.StreamReader.CurrentEncoding%2A>-spezifischen Präambel (z.B. einer Bytereihenfolge-Marke) versucht, die richtige <xref:System.IO.StreamReader.CurrentEncoding%2A> für einen bestimmten Stream zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="49998-138"><xref:System.IO.StreamReader> has a constructor that attempts to ascertain the correct <xref:System.IO.StreamReader.CurrentEncoding%2A> for a given stream, based on the presence of a <xref:System.IO.StreamReader.CurrentEncoding%2A>-specific preamble, such as a byte order mark.</span></span>|  
|<xref:System.IO.StreamWriter?displayProperty=fullName>|<span data-ttu-id="49998-139">Schreibt Zeichen in einen `FileStream`, wobei <xref:System.IO.StreamWriter.Encoding%2A> zum Konvertieren von Zeichen in und aus Bytes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="49998-139">Writes characters to a `FileStream`, using <xref:System.IO.StreamWriter.Encoding%2A> to convert characters to bytes.</span></span>|  
|<xref:System.IO.StringReader?displayProperty=fullName>|<span data-ttu-id="49998-140">Liest Zeichen aus einem `String`.</span><span class="sxs-lookup"><span data-stu-id="49998-140">Reads characters from a `String`.</span></span> <span data-ttu-id="49998-141">Die Ausgabe kann entweder ein Stream in einer beliebigen Codierung oder ein `String` sein.</span><span class="sxs-lookup"><span data-stu-id="49998-141">Output can be either a stream in any encoding or a `String`.</span></span>|  
|<xref:System.IO.StringWriter?displayProperty=fullName>|<span data-ttu-id="49998-142">Schreibt Zeichen an einen `String`.</span><span class="sxs-lookup"><span data-stu-id="49998-142">Writes characters to a `String`.</span></span> <span data-ttu-id="49998-143">Die Ausgabe kann entweder ein Stream in einer beliebigen Codierung oder ein `String` sein.</span><span class="sxs-lookup"><span data-stu-id="49998-143">Output can be either a stream in any encoding or a `String`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49998-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49998-144">See Also</span></span>  
 <span data-ttu-id="49998-145">[Erstellen von Datenströmen](https://msdn.microsoft.com/library/e4y2dch9) </span><span class="sxs-lookup"><span data-stu-id="49998-145">[Composing Streams](https://msdn.microsoft.com/library/e4y2dch9) </span></span>  
 <span data-ttu-id="49998-146">[Datei- und Stream-E/A](https://msdn.microsoft.com/library/k3352a4t) </span><span class="sxs-lookup"><span data-stu-id="49998-146">[File and Stream I/O](https://msdn.microsoft.com/library/k3352a4t) </span></span>  
 <span data-ttu-id="49998-147">[Asynchrone Datei-E/A](https://msdn.microsoft.com/library/kztecsys) </span><span class="sxs-lookup"><span data-stu-id="49998-147">[Asynchronous File I/O](https://msdn.microsoft.com/library/kztecsys) </span></span>  
 [<span data-ttu-id="49998-148">Grundlagen zu Datei-E/A-Vorgängen und dem Dateisystem in .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49998-148">Basics of .NET Framework File I/O and the File System (Visual Basic)</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)

