---
title: Übersicht über Grafiken
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: f0e2fd9dcf31e5fdce16b5a3b6fd21eab6eab66a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505321"
---
# <a name="overview-of-graphics"></a><span data-ttu-id="564a8-102">Übersicht über Grafiken</span><span class="sxs-lookup"><span data-stu-id="564a8-102">Overview of Graphics</span></span>
<span data-ttu-id="564a8-103">GDI + ist eine Anwendungsprogrammierschnittstelle (API), die das Subsystem des Betriebssystems Microsoft Windows bildet.</span><span class="sxs-lookup"><span data-stu-id="564a8-103">GDI+ is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> <span data-ttu-id="564a8-104">GDI + ist verantwortlich für die Anzeige von Informationen auf Bildschirmen und Druckern.</span><span class="sxs-lookup"><span data-stu-id="564a8-104">GDI+ is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="564a8-105">Wie der Name schon sagt, wird der Nachfolger von GDI, die Graphics Device Interface enthalten, die mit früheren Versionen von Windows von GDI + ist.</span><span class="sxs-lookup"><span data-stu-id="564a8-105">As its name suggests, GDI+ is the successor to GDI, the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="564a8-106">Schnittstelle für verwaltete Klassen</span><span class="sxs-lookup"><span data-stu-id="564a8-106">Managed Class Interface</span></span>  
 <span data-ttu-id="564a8-107">Die GDI +-API wird über eine Reihe von Klassen, die als verwalteter Code verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="564a8-107">The GDI+ API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="564a8-108">Dieser Satz von Klassen heißt die *Schnittstelle für verwaltete Klassen* in GDI +.</span><span class="sxs-lookup"><span data-stu-id="564a8-108">This set of classes is called the *managed class interface* to GDI+.</span></span> <span data-ttu-id="564a8-109">Die Schnittstelle für verwaltete Klassen besteht aus den folgenden Namespaces:</span><span class="sxs-lookup"><span data-stu-id="564a8-109">The following namespaces make up the managed class interface:</span></span>  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="564a8-110">Mit einem Graphics Device Interface wie GDI + können Sie die Informationen auf einem Bildschirm oder Drucker anzeigen, ohne sich Gedanken über die Details des jeweiligen Ausgabegeräts machen.</span><span class="sxs-lookup"><span data-stu-id="564a8-110">With a Graphics Device Interface, such as GDI+, you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="564a8-111">Der Programmierer ruft Methoden, die von GDI +-Klassen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="564a8-111">The programmer makes calls to methods provided by GDI+ classes.</span></span> <span data-ttu-id="564a8-112">In diesen Methoden wiederum werden die speziellen Gerätetreiber aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="564a8-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> <span data-ttu-id="564a8-113">GDI + isoliert die Anwendung von der Grafikhardware.</span><span class="sxs-lookup"><span data-stu-id="564a8-113">GDI+ insulates the application from the graphics hardware.</span></span> <span data-ttu-id="564a8-114">Es ist diese Isolierung, die Programmierer geräteunabhängige Anwendungen erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="564a8-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="564a8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="564a8-115">See also</span></span>

- [<span data-ttu-id="564a8-116">Übersicht über Grafiken</span><span class="sxs-lookup"><span data-stu-id="564a8-116">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
