---
title: 'Vorgehensweise: Hinzufügen mehrerer Gruppen von Einstellungen zur Anwendung in C#'
description: Erfahren Sie, wie Sie Ihrer Anwendung in c# mithilfe von Visual Studio mehrere Sätze von Windows Forms Einstellungen hinzufügen.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 579374ff101758b3224bc122c46b891280ed2609
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173444"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>Gewusst wie: Hinzufügen mehrerer Einstellungs Sätze zu Ihrer Anwendung in C\#

In einigen Fällen möchten Sie möglicherweise mehrere Einstellungs Sätze in einer Anwendung haben. Wenn Sie z. b. eine Anwendung entwickeln, in der eine bestimmte Gruppe von Einstellungen häufig geändert werden soll, kann es ratsam sein, Sie in eine einzelne Datei aufzuteilen, damit die Datei im Einzelhandel ersetzt werden kann, sodass andere Einstellungen nicht betroffen sind. Mit Visual Studio können Sie Ihrem Projekt mehrere Einstellungs Sätze hinzufügen. Auf zusätzliche Einstellungs Sätze kann über das-Objekt zugegriffen werden `Properties.Settings` .

## <a name="add-an-additional-set-of-settings"></a>Zusätzlichen Einstellungs Satz hinzufügen

1. Wählen Sie in Visual Studio im Menü **Projekt** die Option **Neues Element hinzufügen**aus.

   Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.

2. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Einstellungsdatei**aus, geben Sie einen Namen für die Datei ein, und klicken Sie auf **Hinzufügen** , um der Projekt Mappe eine neue Einstellungsdatei hinzuzufügen.

3. Ziehen Sie die neue Einstellungsdatei in **Projektmappen-Explorer**in den Ordner **Properties** . Dadurch können Ihre neuen Einstellungen im Code verfügbar sein.

4. Fügen Sie die Einstellungen in dieser Datei hinzu, und verwenden Sie Sie wie jede andere Einstellungsdatei. Sie können über das-Objekt auf diese Gruppe von Einstellungen zugreifen `Properties.Settings` .

## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](using-application-settings-and-user-settings.md)
- [Übersicht über Anwendungseinstellungen](application-settings-overview.md)
