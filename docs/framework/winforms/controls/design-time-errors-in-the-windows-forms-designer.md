---
title: Entwurfszeitfehler im Windows Forms-Designer
ms.date: 03/30/2017
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cce9baf1523391e281593428b633c401103b42b5
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015973"
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a>Entwurfs Zeitfehler im Windows Forms-Designer

In diesem Thema werden die Bedeutung und die Verwendung der Entwurfszeit-Fehlerliste erläutert, die in Visual Studio angezeigt wird, wenn das Windows Forms-Designer nicht geladen werden kann. Wenn diese Fehlerliste angezeigt wird, sollten Sie sie nicht als Fehler im Designer, sondern als Hilfe beim Beheben von Fehlern in Ihrem Code interpretieren.

Ein grundlegendes Verständnis dieser Fehlerliste hilft Ihnen beim Debuggen Ihrer Anwendungen, indem detaillierte Informationen zu den Fehlern und mögliche Lösungen vorgeschlagen werden.

## <a name="the-design-time-error-list-interface"></a>Die Schnittstelle zur Entwurfszeit-Fehlerliste

Wenn das Windows Forms-Designer nicht geladen werden kann, wird im Designer eine Fehlerliste angezeigt. Die Fehler werden in Kategorien gruppiert. Wenn Sie beispielsweise über vier Instanzen von nicht deklarierten Variablen verfügen, werden diese in der gleichen Fehlerkategorie gruppiert. Jede Fehlerkategorie enthält eine kurze Beschreibung, die den Fehler zusammenfasst.

Sie können eine Fehlerkategorie erweitern oder reduzieren, indem Sie auf die Überschrift der Fehlerkategorie klicken oder indem Sie auf das Chevron zum Erweitern/Reduzieren klicken. Wenn Sie eine Fehlerkategorie erweitern, wird folgende zusätzliche Hilfe angezeigt:

- Instanzen dieses Fehlers.

- Hilfe zu diesem Fehler.

- Forenbeiträge zu diesem Fehler.

### <a name="instances-of-this-error"></a>Instanzen dieses Fehlers

In der zusätzlichen Hilfe werden alle Instanzen des Fehlers im aktuellen Projekt aufgeführt. Viele Fehler enthalten eine genaue Position im folgenden Format: *[Projektname]* *[Formularname]* Zeile: *[Zeilennummer]* Spalte: *[Spaltennummer]* . Über den Link **Gehe zu Code** gelangen Sie zu der Position im Code, an der der Fehler auftritt.

Wenn dem Fehler eine Aufrufliste zugeordnet ist, können Sie zur näheren Erläuterung des Fehlers auf den Link **Aufrufliste anzeigen** klicken, um die Aufrufliste anzuzeigen. Durch Überprüfen des Stapels können Sie wertvolle Debuginformationen erhalten. Sie können beispielsweise die Funktionen nachverfolgen, die vor Auftreten des Fehlers aufgerufen wurden. Die Aufrufliste ist auswählbar, sodass sie kopiert und gespeichert werden kann.

> [!NOTE]
> In Visual Basic wird in der Entwurfszeit-Fehlerliste nicht mehr als ein Fehler angezeigt, es können jedoch mehrere Instanzen desselben Fehlers angezeigt werden. In Visual C++ weisen die Fehler keine Verknüpfungen mit GoTo-Codes/Zeilennummern auf.

### <a name="forum-posts-about-this-error"></a>Forumbeiträge zu diesem Fehler

Die zusätzliche Hilfe enthält einen Link zu Forumsbeiträgen im Zusammenhang mit dem Fehler. Die Foren werden basierend auf der Zeichenfolge der Fehlermeldung durchsucht. Sie können auch versuchen, die Suche in den folgenden Foren durchführen:

- [Windows Forms-Designer Forum](https://social.msdn.microsoft.com/Forums/windows/home?forum=winformsdesigner)

- [Windows Forms Forum](https://social.msdn.microsoft.com/Forums/windows/home?category=windowsforms)

### <a name="ignore-and-continue"></a>Ignorieren und fortfahren

Sie können die Fehlerbedingung ignorieren und mit dem Laden des Designers fortfahren. Die Auswahl dieser Aktion kann zu unerwartetem Verhalten führen. Beispielsweise werden Steuerelemente möglicherweise nicht auf der Entwurfsoberfläche angezeigt.

## <a name="see-also"></a>Siehe auch

- [Problembehandlung bei der Entwurfszeit Entwicklung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))
- [Problembehandlung beim Erstellen von Komponenten und Steuerelementen](troubleshooting-control-and-component-authoring.md)
- [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](developing-windows-forms-controls-at-design-time.md)
- [Fehlermeldungen im Windows Forms-Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))
