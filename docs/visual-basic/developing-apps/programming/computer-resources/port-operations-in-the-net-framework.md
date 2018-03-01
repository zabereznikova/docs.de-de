---
title: "Operationen für serielle Anschlüsse in .NET Framework mit Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- ports, Visual Basic
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 77b8a464f2f64f701a5b99690756c0f22a410064
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a><span data-ttu-id="9695b-102">Operationen für serielle Anschlüsse in .NET Framework mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9695b-102">Port Operations in the .NET Framework with Visual Basic</span></span>
<span data-ttu-id="9695b-103">Sie können auf die seriellen Anschlüsse Ihres Computers über die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]-Klassen im Namespace <xref:System.IO.Ports?displayProperty=nameWithType> zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9695b-103">You can access your computer's serial ports through the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="9695b-104">Die wichtigste Klasse, <xref:System.IO.Ports.SerialPort>, bietet ein Framework für synchrone und ereignisgesteuerte E/A-Vorgänge, Zugriff auf Pin- und Unterbrechungszustände sowie Zugriff auf die Treibereigenschaften für den seriellen Anschluss.</span><span class="sxs-lookup"><span data-stu-id="9695b-104">The most important class, <xref:System.IO.Ports.SerialPort>, provides a framework for synchronous and event-driven I/O, access to pin and break states, and access to serial driver properties.</span></span> <span data-ttu-id="9695b-105">Sie kann von einem <xref:System.IO.Stream>-Objekt umschlossen werden, auf das durch die Eigenschaft <xref:System.IO.Ports.SerialPort.BaseStream> zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9695b-105">It can be wrapped in a <xref:System.IO.Stream> object, accessible through the <xref:System.IO.Ports.SerialPort.BaseStream> property.</span></span> <span data-ttu-id="9695b-106">Durch die Umschließung von <xref:System.IO.Ports.SerialPort> in einem <xref:System.IO.Stream>-Objekt kann auf den seriellen Anschluss von Klassen zugegriffen werden, die Streams verwenden.</span><span class="sxs-lookup"><span data-stu-id="9695b-106">Wrapping <xref:System.IO.Ports.SerialPort> in a <xref:System.IO.Stream> object allows the serial port to be accessed by classes that use streams.</span></span> <span data-ttu-id="9695b-107">Der Namespace enthält Enumerationen, die die Steuerung von seriellen Anschlüssen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="9695b-107">The namespace includes enumerations that simplify the control of serial ports.</span></span>  
  
 <span data-ttu-id="9695b-108">Die einfachste Möglichkeit zum Erstellen eines <xref:System.IO.Ports.SerialPort>-Objekts besteht darin, die Methode <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A> zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9695b-108">The simplest way to create a <xref:System.IO.Ports.SerialPort> object is through the <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9695b-109">Sie können [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]-Klassen nicht verwenden, um direkt auf andere Porttypen wie Parallelanschlüsse, USB-Anschlüsse usw. zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9695b-109">You cannot use [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes to directly access other types of ports, such as parallel ports, USB ports, and so on.</span></span>  
  
## <a name="enumerations"></a><span data-ttu-id="9695b-110">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="9695b-110">Enumerations</span></span>  
 <span data-ttu-id="9695b-111">Diese Tabelle enthält und beschreibt die wichtigsten Enumerationen für den Zugriff auf einen seriellen Anschluss:</span><span class="sxs-lookup"><span data-stu-id="9695b-111">This table lists and describes the main enumerations used for accessing a serial port:</span></span>  
  
|<span data-ttu-id="9695b-112">Enumeration</span><span class="sxs-lookup"><span data-stu-id="9695b-112">Enumeration</span></span>|<span data-ttu-id="9695b-113">description</span><span class="sxs-lookup"><span data-stu-id="9695b-113">Description</span></span>|  
|---|---|   
|<xref:System.IO.Ports.Handshake>|<span data-ttu-id="9695b-114">Gibt das Steuerungsprotokoll an, das beim Herstellen einer Kommunikation eines seriellen Anschlusses für ein <xref:System.IO.Ports.SerialPort>-Objekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9695b-114">Specifies the control protocol used in establishing a serial port communication for a <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.Parity>|<span data-ttu-id="9695b-115">Gibt das Paritätsbit für ein <xref:System.IO.Ports.SerialPort>-Objekt an.</span><span class="sxs-lookup"><span data-stu-id="9695b-115">Specifies the parity bit for a <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.SerialData>|<span data-ttu-id="9695b-116">Gibt den Zeichentyp an, der an einem seriellen Anschluss des <xref:System.IO.Ports.SerialPort>-Objekts empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="9695b-116">Specifies the type of character that was received on the serial port of the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.SerialError>|<span data-ttu-id="9695b-117">Gibt die Fehler für das <xref:System.IO.Ports.SerialPort>-Objekt an.</span><span class="sxs-lookup"><span data-stu-id="9695b-117">Specifies errors that occur on the <xref:System.IO.Ports.SerialPort> object</span></span>|  
|<xref:System.IO.Ports.SerialPinChange>|<span data-ttu-id="9695b-118">Gibt die Art der Änderungen für das <xref:System.IO.Ports.SerialPort>-Objekt an.</span><span class="sxs-lookup"><span data-stu-id="9695b-118">Specifies the type of change that occurred on the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.StopBits>|<span data-ttu-id="9695b-119">Gibt die Anzahl von Stoppbits an, die das <xref:System.IO.Ports.SerialPort>-Objekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="9695b-119">Specifies the number of stop bits used on the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9695b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9695b-120">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Ports>  
 [<span data-ttu-id="9695b-121">Zugreifen auf die Anschlüsse des Computers</span><span class="sxs-lookup"><span data-stu-id="9695b-121">Accessing the Computer's Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md)
