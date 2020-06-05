---
title: Zugreifen auf Computerressourcen
ms.date: 07/20/2015
helpviewer_keywords:
- computer resources [Visual Basic]
- My.Computer object [Visual Basic], tasks
- computer resources [Visual Basic], accessing
ms.assetid: 75b81c88-f7c0-46e0-95c8-0c006d2120f9
ms.openlocfilehash: 9595abaa1daa2b4a4436577d58856183dcb4d9ac
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401783"
---
# <a name="accessing-computer-resources-visual-basic"></a><span data-ttu-id="4c7ca-102">Zugreifen auf Computerressourcen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c7ca-102">Accessing computer resources (Visual Basic)</span></span>

<span data-ttu-id="4c7ca-103">Das `My.Computer`-Objekt ist eines der drei zentralen Objekte in `My` und bietet Zugriff auf Informationen und häufig verwendete Funktionen.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-103">The `My.Computer` object is one of the three central objects in `My`, providing access to information and commonly used functionality.</span></span> <span data-ttu-id="4c7ca-104">`My.Computer` bietet Methoden, Eigenschaften und Ereignisse für den Zugriff auf den Computer, auf dem die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-104">`My.Computer` provides methods, properties, and events for accessing the computer on which the application is running.</span></span> <span data-ttu-id="4c7ca-105">Es enthält folgende Objekte:</span><span class="sxs-lookup"><span data-stu-id="4c7ca-105">Its objects include:</span></span>

- <xref:Microsoft.VisualBasic.Devices.Audio>
- <span data-ttu-id="4c7ca-106">Zwischenablage (<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>)</span><span class="sxs-lookup"><span data-stu-id="4c7ca-106">Clipboard (<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>)</span></span>
- <xref:Microsoft.VisualBasic.Devices.Clock>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.Devices.ServerComputer.Info%2A>
- <xref:Microsoft.VisualBasic.Devices.Keyboard>
- <xref:Microsoft.VisualBasic.Devices.Mouse>
- <xref:Microsoft.VisualBasic.Devices.Network>
- <xref:Microsoft.VisualBasic.Devices.Ports>
- <span data-ttu-id="4c7ca-107">Registrierung (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)</span><span class="sxs-lookup"><span data-stu-id="4c7ca-107">Registry (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4c7ca-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4c7ca-108">In this section</span></span>

[<span data-ttu-id="4c7ca-109">Wiedergabe von Sound</span><span class="sxs-lookup"><span data-stu-id="4c7ca-109">Playing Sounds</span></span>](playing-sounds.md)  
<span data-ttu-id="4c7ca-110">Führt Aufgaben im Zusammenhang mit `My.Computer.Audio` auf wie die Wiedergabe eines Sounds im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-110">Lists tasks associated with `My.Computer.Audio`, such as playing a sound in the background.</span></span>

[<span data-ttu-id="4c7ca-111">Speichern von Daten in der Zwischenablage und Lesen von Daten aus der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="4c7ca-111">Storing Data to and Reading from the Clipboard</span></span>](storing-data-to-and-reading-from-the-clipboard.md)  
<span data-ttu-id="4c7ca-112">Führt Aufgaben im Zusammenhang mit `My.Computer.Clipboard` auf wie das Lesen von Daten aus oder das Schreiben von Daten in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-112">Lists tasks associated with `My.Computer.Clipboard`, such as reading data from or writing data to the Clipboard.</span></span>

[<span data-ttu-id="4c7ca-113">Abrufen von Informationen über den Computer</span><span class="sxs-lookup"><span data-stu-id="4c7ca-113">Getting Information about the Computer</span></span>](getting-information-about-the-computer.md)  
<span data-ttu-id="4c7ca-114">Führt Aufgaben im Zusammenhang mit `My.Computer.Info` auf wie das Bestimmen des vollständigen Namens oder der IP-Adressen eines Computers.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-114">Lists tasks associated with `My.Computer.Info`, such as determining a computer's full name or IP addresses.</span></span>

[<span data-ttu-id="4c7ca-115">Zugreifen auf die Tastatur</span><span class="sxs-lookup"><span data-stu-id="4c7ca-115">Accessing the Keyboard</span></span>](accessing-the-keyboard.md)  
<span data-ttu-id="4c7ca-116">Führt Aufgaben im Zusammenhang mit `My.Computer.Keyboard` auf wie das Bestimmen, ob die FESTSTELLTASTE aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-116">Lists tasks associated with `My.Computer.Keyboard`, such as determining whether CAPS LOCK is on.</span></span>

[<span data-ttu-id="4c7ca-117">Zugreifen auf die Maus</span><span class="sxs-lookup"><span data-stu-id="4c7ca-117">Accessing the Mouse</span></span>](accessing-the-mouse.md)  
<span data-ttu-id="4c7ca-118">Führt Aufgaben im Zusammenhang mit `My.Computer.Mouse` auf wie das Bestimmen, ob eine Maus vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-118">Lists tasks associated with `My.Computer.Mouse`, such as determining whether a mouse is present.</span></span>

[<span data-ttu-id="4c7ca-119">Durchführen von Netzwerkvorgängen</span><span class="sxs-lookup"><span data-stu-id="4c7ca-119">Performing Network Operations</span></span>](performing-network-operations.md)  
<span data-ttu-id="4c7ca-120">Führt Aufgaben im Zusammenhang mit `My.Computer.Network` auf wie das Hochladen oder Herunterladen von Dateien.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-120">Lists tasks associated with `My.Computer.Network`, such as uploading or downloading files.</span></span>

[<span data-ttu-id="4c7ca-121">Zugreifen auf die Anschlüsse des Computers</span><span class="sxs-lookup"><span data-stu-id="4c7ca-121">Accessing the Computer's Ports</span></span>](accessing-the-computer-s-ports.md)  
<span data-ttu-id="4c7ca-122">Führt Aufgaben im Zusammenhang mit `My.Computer.Ports` auf wie das Anzeigen der verfügbaren seriellen Anschlüsse oder das Senden von Zeichenfolgen an serielle Anschlüsse.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-122">Lists tasks associated with `My.Computer.Ports`, such as showing available serial ports or sending strings to serial ports.</span></span>

[<span data-ttu-id="4c7ca-123">Lesen aus der und Schreiben in die Registrierung</span><span class="sxs-lookup"><span data-stu-id="4c7ca-123">Reading from and Writing to the Registry</span></span>](reading-from-and-writing-to-the-registry.md)  
<span data-ttu-id="4c7ca-124">Führt Aufgaben im Zusammenhang mit `My.Computer.Registry` auf wie das Lesen von Daten aus oder das Schreiben von Daten an Registrierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="4c7ca-124">Lists tasks associated with `My.Computer.Registry`, such as reading data from or writing data to registry keys.</span></span>
