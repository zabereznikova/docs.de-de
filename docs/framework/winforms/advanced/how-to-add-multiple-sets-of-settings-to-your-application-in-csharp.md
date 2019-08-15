---
title: 'Vorgehensweise: Hinzufügen mehrerer Gruppen von Einstellungen zur Anwendung in C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: c6842d11c04e905d42734af939f2c3f0cfeacd47
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040124"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>Vorgehensweise: Fügen Sie Ihrer Anwendung mehrere Einstellungs Sätze in C hinzu.\#

In einigen Fällen möchten Sie möglicherweise mehrere Einstellungs Sätze in einer Anwendung haben. Wenn Sie z. b. eine Anwendung entwickeln, in der eine bestimmte Gruppe von Einstellungen häufig geändert werden soll, kann es ratsam sein, Sie in eine einzelne Datei aufzuteilen, damit die Datei im Einzelhandel ersetzt werden kann, sodass andere Einstellungen nicht betroffen sind. Mit Visual Studio können Sie Ihrem Projekt mehrere Einstellungs Sätze hinzufügen. Auf zusätzliche Einstellungs Sätze kann über das `Properties.Settings` -Objekt zugegriffen werden.

## <a name="add-an-additional-set-of-settings"></a>Zusätzlichen Einstellungs Satz hinzufügen

1. Wählen Sie in Visual Studio im Menü **Projekt** die Option **Neues Element hinzufügen**aus.

   Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.

2. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Einstellungsdatei**aus, geben Sie einen Namen für die Datei ein, und klicken Sie auf **Hinzufügen** , um der Projekt Mappe eine neue Einstellungsdatei hinzuzufügen.

3. Ziehen Sie die neue Einstellungsdatei in **Projektmappen-Explorer**in den Ordner **Properties** . Dadurch können Ihre neuen Einstellungen im Code verfügbar sein.

4. Fügen Sie die Einstellungen in dieser Datei hinzu, und verwenden Sie Sie wie jede andere Einstellungsdatei. Sie können über das `Properties.Settings` -Objekt auf diese Gruppe von Einstellungen zugreifen.

## <a name="see-also"></a>Siehe auch

- [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](using-application-settings-and-user-settings.md)
- [Übersicht über Anwendungseinstellungen](application-settings-overview.md)
