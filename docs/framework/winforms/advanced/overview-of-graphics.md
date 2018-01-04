---
title: "Übersicht über Grafiken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3438fe2f1c3a6fc40efda0ff2583208f38bf7d5c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="overview-of-graphics"></a>Übersicht über Grafiken
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]ist eine Anwendungsprogrammierschnittstelle (API), die das Subsystem des Betriebssystems Microsoft Windows bildet. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]ist verantwortlich für das Anzeigen von Informationen auf Bildschirmen und Druckern. Wie der Name andeutet, ist [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] der Nachfolger von [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], die Schnittstelle für Grafikgeräte (Graphics Device Interface), die in früheren Versionen von Windows enthalten ist.  
  
## <a name="managed-class-interface"></a>Schnittstelle für verwaltete Klassen  
 Die [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API verfügbar gemacht wird, über eine Reihe von Klassen, die als verwalteter Code bereitgestellt. Dieser Satz von Klassen wird aufgerufen, die *Schnittstelle für verwaltete Klassen* auf [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Die Schnittstelle für verwaltete Klassen besteht aus den folgenden Namespaces:  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 Mit einem Graphics Device Interface wie z. B. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], Sie können die Informationen auf einem Bildschirm oder Drucker anzeigen, ohne sich Sorgen über die Details des jeweiligen Ausgabegeräts werden. Der Programmierer ruft Methoden auf, die von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]-Klassen bereitgestellt werden. In diesen Methoden wiederum werden die speziellen Gerätetreiber aufgerufen. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] isoliert die jeweilige Anwendung von der Grafikhardware. Es ist diese Isolierung, mit der Programmierer geräteunabhängige Anwendungen erstellen kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Grafiken](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)
