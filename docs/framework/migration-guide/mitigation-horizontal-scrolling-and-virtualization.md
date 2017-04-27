---
title: "Entschärfung: Horizontales Scrollen und Virtualisierung | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5bafd9b-a3b3-4f92-8241-2aad254fb1a9
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 37c60fd8a3e3e4e44dc00e278f6edafcdd766c03
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-horizontal-scrolling-and-virtualization"></a>Entschärfung: Horizontales Scrollen und Virtualisierung
Diese Änderung betrifft <xref:System.Windows.Controls.ItemsControl>-Steuerelemente mit eigener Virtualisierung in der senkrecht zur Hauptscrollrichtung stehenden Richtung. (Das beste Beispiel ist ein <xref:System.Windows.Controls.DataGrid>-Steuerelement mit auf `true` festgelegter <xref:System.Windows.Controls.DataGrid.EnableColumnVirtualization%2A>.)  Das Ergebnis bestimmter horizontaler Scrollvorgänge wurde geändert, um Ergebnisse zu erzeugen, die intuitiver und in höheren Maß analog zu den Ergebnissen vergleichbarer vertikaler Vorgänge sind.  Zu den Vorgängen gehören im Einzelnen **Bildlauf hierhin durchführen** und **Rechte Kante**, um die Namen aus dem Menü zu verwenden, das durch Klicken mit der rechten Maustaste auf eine horizontale Scrollleiste angezeigt wird.  Beide Befehle berechnen einen Kandidatenoffset und rufen <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset%2A?displayProperty=fullName> auf.  Nach dem Scrollen zum neuen Offset hat sich die Definition von „hierhin“ oder „rechte Kante“ möglicherweise geändert, da die neuen entvirtualisierten Inhalte den Wert von <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A?displayProperty=fullName> geändert haben.  
  
## <a name="description-of-the-change"></a>Beschreibung der Änderung  
 Vor [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] verwendet der Scrollvorgang einfach den Kandidatenoffset, obwohl er möglicherweise nicht mehr „hierhin“ oder „rechte Kante“ darstellt.  Dies führt zu Effekten wie einem „Springen“ des Leistenziehpunkts, die sich am besten durch ein Beispiel veranschaulichen lassen.  Nehmen wir an, für ein <xref:System.Windows.Controls.DataGrid>-Steuerelement ist <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> auf 1000 und <xref:System.Windows.FrameworkElement.Width%2A> auf 200 festgelegt.  Ein Scrollen zu „Rechte Kante“ verwendet den Kandidatenoffset 1000 - 200 = 800.  Beim Scrollen zu diesem Offset werden neue Spalten entvirtualisiert; nehmen wir an, dass sie sehr breit sind, sodass sich <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> zu 2000 ändert.  Der Scrollvorgang endet mit <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A>=800, und der Leistenziehpunkt „springt“ nahezu zur Mitte der Scrollleiste zurück – genau zu 800/2000 = 40 %.  
  
 Von [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an wird beim Eintreten dieser Situation ein neuer Kandidatenoffset berechnet. (Beim vertikalen Scrollen wurde dies bereits implementiert.)  
  
## <a name="impact"></a>Auswirkungen  
 Die Änderung ergibt ein besser vorhersehbares und intuitiveres Verhalten für den Endbenutzer, sie kann sich aber auch auf jede App auswirken, die auf den genauen Wert von <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> nach einem horizontalen Scrollvorgang angewiesen ist, gleich ob er vom Endbenutzer oder durch einen expliziten Aufruf von <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset%2A?displayProperty=fullName> ausgelöst wurde.  
  
## <a name="mitigation"></a>Problemumgehung  
 Eine App, die einen vorhergesagten Wert für <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> verwendet, sollte dahingehend geändert werden, dass sie nach jedem horizontalen Scrollen, das aufgrund der Entvirtualisierung den Wert von <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> ändern kann, den tatsächlichen Wert (und den Wert von <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A>) abruft.  
  
## <a name="see-also"></a>Siehe auch  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)
