---
title: Operationen für serielle Anschlüsse in .NET Framework
ms.date: 07/20/2015
helpviewer_keywords:
- ports, Visual Basic
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
ms.openlocfilehash: 68f0c67b8135c6bb7ce8a134e2a324bc12c0aad9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345505"
---
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a><span data-ttu-id="75cd1-102">Operationen für serielle Anschlüsse in .NET Framework mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75cd1-102">Port Operations in the .NET Framework with Visual Basic</span></span>

<span data-ttu-id="75cd1-103">Sie können auf die seriellen Anschlüsse Ihres Computers über die .NET Framework-Klassen im Namespace <xref:System.IO.Ports?displayProperty=nameWithType> zugreifen.</span><span class="sxs-lookup"><span data-stu-id="75cd1-103">You can access your computer's serial ports through the .NET Framework classes in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="75cd1-104">Die wichtigste Klasse, <xref:System.IO.Ports.SerialPort>, bietet ein Framework für synchrone und ereignisgesteuerte E/A-Vorgänge, Zugriff auf Pin- und Unterbrechungszustände sowie Zugriff auf die Treibereigenschaften für den seriellen Anschluss.</span><span class="sxs-lookup"><span data-stu-id="75cd1-104">The most important class, <xref:System.IO.Ports.SerialPort>, provides a framework for synchronous and event-driven I/O, access to pin and break states, and access to serial driver properties.</span></span> <span data-ttu-id="75cd1-105">Sie kann von einem <xref:System.IO.Stream>-Objekt umschlossen werden, auf das durch die Eigenschaft <xref:System.IO.Ports.SerialPort.BaseStream> zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="75cd1-105">It can be wrapped in a <xref:System.IO.Stream> object, accessible through the <xref:System.IO.Ports.SerialPort.BaseStream> property.</span></span> <span data-ttu-id="75cd1-106">Durch die Umschließung von <xref:System.IO.Ports.SerialPort> in einem <xref:System.IO.Stream>-Objekt kann auf den seriellen Anschluss von Klassen zugegriffen werden, die Streams verwenden.</span><span class="sxs-lookup"><span data-stu-id="75cd1-106">Wrapping <xref:System.IO.Ports.SerialPort> in a <xref:System.IO.Stream> object allows the serial port to be accessed by classes that use streams.</span></span> <span data-ttu-id="75cd1-107">Der Namespace enthält Enumerationen, die die Steuerung von seriellen Anschlüssen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="75cd1-107">The namespace includes enumerations that simplify the control of serial ports.</span></span>

<span data-ttu-id="75cd1-108">Die einfachste Möglichkeit zum Erstellen eines <xref:System.IO.Ports.SerialPort>-Objekts besteht darin, die Methode <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A> zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="75cd1-108">The simplest way to create a <xref:System.IO.Ports.SerialPort> object is through the <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A> method.</span></span>

> [!NOTE]
> <span data-ttu-id="75cd1-109">Sie können .NET Framework-Klassen nicht verwenden, um direkt auf andere Porttypen wie Parallelanschlüsse, USB-Anschlüsse usw. zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="75cd1-109">You cannot use .NET Framework classes to directly access other types of ports, such as parallel ports, USB ports, and so on.</span></span>

## <a name="enumerations"></a><span data-ttu-id="75cd1-110">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="75cd1-110">Enumerations</span></span>

<span data-ttu-id="75cd1-111">Diese Tabelle enthält und beschreibt die wichtigsten Enumerationen für den Zugriff auf einen seriellen Anschluss:</span><span class="sxs-lookup"><span data-stu-id="75cd1-111">This table lists and describes the main enumerations used for accessing a serial port:</span></span>

|<span data-ttu-id="75cd1-112">Enumeration</span><span class="sxs-lookup"><span data-stu-id="75cd1-112">Enumeration</span></span>|<span data-ttu-id="75cd1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75cd1-113">Description</span></span>|
|---|---|
|<xref:System.IO.Ports.Handshake>|<span data-ttu-id="75cd1-114">Gibt das Steuerungsprotokoll an, das beim Herstellen einer Kommunikation eines seriellen Anschlusses für ein <xref:System.IO.Ports.SerialPort>-Objekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="75cd1-114">Specifies the control protocol used in establishing a serial port communication for a <xref:System.IO.Ports.SerialPort> object.</span></span>|
|<xref:System.IO.Ports.Parity>|<span data-ttu-id="75cd1-115">Gibt das Paritätsbit für ein <xref:System.IO.Ports.SerialPort>-Objekt an.</span><span class="sxs-lookup"><span data-stu-id="75cd1-115">Specifies the parity bit for a <xref:System.IO.Ports.SerialPort> object.</span></span>|
|<xref:System.IO.Ports.SerialData>|<span data-ttu-id="75cd1-116">Gibt den Zeichentyp an, der an einem seriellen Anschluss des <xref:System.IO.Ports.SerialPort>-Objekts empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="75cd1-116">Specifies the type of character that was received on the serial port of the <xref:System.IO.Ports.SerialPort> object.</span></span>|
|<xref:System.IO.Ports.SerialError>|<span data-ttu-id="75cd1-117">Gibt die Fehler für das <xref:System.IO.Ports.SerialPort>-Objekt an.</span><span class="sxs-lookup"><span data-stu-id="75cd1-117">Specifies errors that occur on the <xref:System.IO.Ports.SerialPort> object</span></span>|
|<xref:System.IO.Ports.SerialPinChange>|<span data-ttu-id="75cd1-118">Gibt die Art der Änderungen für das <xref:System.IO.Ports.SerialPort>-Objekt an.</span><span class="sxs-lookup"><span data-stu-id="75cd1-118">Specifies the type of change that occurred on the <xref:System.IO.Ports.SerialPort> object.</span></span>|
|<xref:System.IO.Ports.StopBits>|<span data-ttu-id="75cd1-119">Gibt die Anzahl von Stoppbits an, die das <xref:System.IO.Ports.SerialPort>-Objekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="75cd1-119">Specifies the number of stop bits used on the <xref:System.IO.Ports.SerialPort> object.</span></span>|

## <a name="see-also"></a><span data-ttu-id="75cd1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75cd1-120">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- [<span data-ttu-id="75cd1-121">Zugreifen auf die Anschlüsse des Computers</span><span class="sxs-lookup"><span data-stu-id="75cd1-121">Accessing the Computer's Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md)
