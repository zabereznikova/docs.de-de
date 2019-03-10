---
title: Übersicht über Grafiken
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: 8d8e1ab286d4e5723f5ca6bca0b6eeff53ac1d43
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711342"
---
# <a name="overview-of-graphics"></a><span data-ttu-id="159b3-102">Übersicht über Grafiken</span><span class="sxs-lookup"><span data-stu-id="159b3-102">Overview of Graphics</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="159b3-103">ist eine Anwendungsprogrammierschnittstelle (API), die das Subsystem des Betriebssystems Microsoft Windows bildet.</span><span class="sxs-lookup"><span data-stu-id="159b3-103">is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="159b3-104">ist verantwortlich für die Anzeige von Informationen auf Bildschirmen und Druckern.</span><span class="sxs-lookup"><span data-stu-id="159b3-104">is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="159b3-105">Wie der Name andeutet, ist [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] der Nachfolger von [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], die Schnittstelle für Grafikgeräte (Graphics Device Interface), die in früheren Versionen von Windows enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="159b3-105">As its name suggests, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is the successor to [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="159b3-106">Schnittstelle für verwaltete Klassen</span><span class="sxs-lookup"><span data-stu-id="159b3-106">Managed Class Interface</span></span>  
 <span data-ttu-id="159b3-107">Die [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API wird über eine Reihe von Klassen, die als verwalteter Code verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="159b3-107">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="159b3-108">Dieser Satz von Klassen heißt die *Schnittstelle für verwaltete Klassen* zu [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="159b3-108">This set of classes is called the *managed class interface* to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="159b3-109">Die Schnittstelle für verwaltete Klassen besteht aus den folgenden Namespaces:</span><span class="sxs-lookup"><span data-stu-id="159b3-109">The following namespaces make up the managed class interface:</span></span>  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="159b3-110">Mit einem Graphics Device Interface wie z. B. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], Sie können die Informationen auf einem Bildschirm oder Drucker anzeigen, ohne sich Gedanken über die Details des jeweiligen Ausgabegeräts machen.</span><span class="sxs-lookup"><span data-stu-id="159b3-110">With a Graphics Device Interface, such as [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="159b3-111">Der Programmierer ruft Methoden auf, die von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]-Klassen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="159b3-111">The programmer makes calls to methods provided by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span> <span data-ttu-id="159b3-112">In diesen Methoden wiederum werden die speziellen Gerätetreiber aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="159b3-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="159b3-113">isoliert die jeweilige Anwendung von der Grafikhardware.</span><span class="sxs-lookup"><span data-stu-id="159b3-113">insulates the application from the graphics hardware.</span></span> <span data-ttu-id="159b3-114">Es ist diese Isolierung, die Programmierer geräteunabhängige Anwendungen erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="159b3-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="159b3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="159b3-115">See also</span></span>
- [<span data-ttu-id="159b3-116">Übersicht über Grafiken</span><span class="sxs-lookup"><span data-stu-id="159b3-116">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
