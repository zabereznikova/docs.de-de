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
# <a name="overview-of-graphics"></a>Übersicht über Grafiken
GDI + ist eine Anwendungsprogrammierschnittstelle (API), die das Subsystem des Betriebssystems Microsoft Windows bildet. GDI + ist verantwortlich für die Anzeige von Informationen auf Bildschirmen und Druckern. Wie der Name schon sagt, wird der Nachfolger von GDI, die Graphics Device Interface enthalten, die mit früheren Versionen von Windows von GDI + ist.  
  
## <a name="managed-class-interface"></a>Schnittstelle für verwaltete Klassen  
 Die GDI +-API wird über eine Reihe von Klassen, die als verwalteter Code verfügbar gemacht. Dieser Satz von Klassen heißt die *Schnittstelle für verwaltete Klassen* in GDI +. Die Schnittstelle für verwaltete Klassen besteht aus den folgenden Namespaces:  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 Mit einem Graphics Device Interface wie GDI + können Sie die Informationen auf einem Bildschirm oder Drucker anzeigen, ohne sich Gedanken über die Details des jeweiligen Ausgabegeräts machen. Der Programmierer ruft Methoden, die von GDI +-Klassen bereitgestellt werden. In diesen Methoden wiederum werden die speziellen Gerätetreiber aufgerufen. GDI + isoliert die Anwendung von der Grafikhardware. Es ist diese Isolierung, die Programmierer geräteunabhängige Anwendungen erstellen kann.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Grafiken](graphics-overview-windows-forms.md)
