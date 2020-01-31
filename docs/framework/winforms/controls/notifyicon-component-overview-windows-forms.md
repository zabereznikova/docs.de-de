---
title: Übersicht über die NotifyIcon-Komponente
ms.date: 03/30/2017
f1_keywords:
- NotifyIcon
helpviewer_keywords:
- NotifyIcon component [Windows Forms], about NotifyIcon component
- system tray icons [Windows Forms], about system tray icons
- system tray icons [Windows Forms], using in Windows Forms
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
ms.openlocfilehash: 587bf514db853f1122ed16abc05a195985c5ce8d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742126"
---
# <a name="notifyicon-component-overview-windows-forms"></a>Übersicht über die NotifyIcon-Komponente (Windows Forms)

Die <xref:System.Windows.Forms.NotifyIcon>-Komponente von Windows Forms wird in der Regel verwendet, um Symbole für Prozesse anzuzeigen, die im Hintergrund ausgeführt werden und für die nur selten eine Benutzeroberfläche angezeigt wird. Ein Beispiel ist ein Virenschutzprogramm, auf das durch Klicken auf ein Symbol im Statusbereich der Taskleiste zugegriffen werden kann.

## <a name="key-properties-of-notifyicons"></a>Haupteigenschaften von NotifyIcons

Jede <xref:System.Windows.Forms.NotifyIcon>-Komponente zeigt ein einzelnes Symbol im Statusbereich an. Wenn drei Hintergrundprozesse ausgeführt werden, für die jeweils ein Symbol angezeigt werden soll, müssen Sie dem Formular drei <xref:System.Windows.Forms.NotifyIcon>-Komponenten hinzufügen. Die wichtigsten Eigenschaften der <xref:System.Windows.Forms.NotifyIcon>-Komponente sind <xref:System.Windows.Forms.NotifyIcon.Icon%2A> und <xref:System.Windows.Forms.NotifyIcon.Visible%2A>. Mit der <xref:System.Windows.Forms.NotifyIcon.Icon%2A>-Eigenschaft wird das Symbol festgelegt, das im Statusbereich angezeigt wird. Damit das Symbol angezeigt wird, muss die <xref:System.Windows.Forms.NotifyIcon.Visible%2A>-Eigenschaft auf `true` festgelegt sein.

## <a name="notifyicons-options"></a>Optionen für NotifyIcons

Sie können SprechblasenInfos, Kontextmenüs und QuickInfos mit einem <xref:System.Windows.Forms.NotifyIcon> verknüpfen, um den Benutzer zu unterstützen.

Sie können eine SprechblasenInfo für ein <xref:System.Windows.Forms.NotifyIcon> anzeigen, indem Sie die <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A>-Methode aufrufen und die Zeitspanne angeben, für die die SprechblasenInfo angezeigt werden soll. Über <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> bzw. <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A> können Sie auch den Text, das Symbol bzw. den Titel der SprechblasenInfo angeben. <xref:System.Windows.Forms.NotifyIcon>-Komponenten können auch zugeordnete QuickInfos und Kontextmenüs haben. Weitere Informationen finden Sie unter Übersicht über die [ToolTip-Komponente](tooltip-component-overview-windows-forms.md) und [Übersicht über die ContextMenu-Komponente](contextmenu-component-overview-windows-forms.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.NotifyIcon>
- [NotifyIcon-Komponente](notifyicon-component-windows-forms.md)
