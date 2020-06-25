---
title: 'Vorgehensweise: Erstellen einer neuen Einstellung zur Entwurfszeit'
description: Erfahren Sie, wie Sie eine neue Windows Forms Einstellung zur Entwurfszeit mithilfe des Einstellungs-Designers in Visual Studio erstellen.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: ce37b42191999e29de2f2f7f7e7abfa0ec3f4d47
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325847"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a>Gewusst wie: Erstellen einer neuen Einstellung zur Entwurfszeit

Sie können eine neue Einstellung zur Entwurfszeit erstellen, indem Sie den Einstellungs-Designer in Visual Studio verwenden. Der Einstellungs-Designer ist eine Schnittstelle im Raster Stil, mit der Sie neue Einstellungen erstellen und Eigenschaften für diese Einstellungen angeben können. Sie müssen Name, Wert, Typ und Bereich für die neuen Einstellungen angeben. Nachdem eine Einstellung erstellt wurde, können Sie im Code darauf zugreifen.

## <a name="create-a-new-setting-at-design-time-in-c"></a>Erstellen einer neuen Einstellung zur Entwurfszeit in C\#

1. Öffnen Sie Visual Studio.

2. Erweitern Sie in **Projektmappen-Explorer**den Knoten **Eigenschaften** des Projekts.

3. Doppelklicken Sie auf die Einstellungsdatei, der Sie eine neue Einstellung hinzufügen möchten. Der Standardname für diese Datei ist Settings. Settings.

4. Legen Sie im Einstellungs-Designer den **Namen**, den **Wert**, den **Typ**und den Gültigkeits **Bereich** für die Einstellung fest. Jede Zeile stellt eine einzelne Einstellung dar.

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a>Erstellen Sie eine neue Einstellung zur Entwurfszeit in Visual Basic

1. Öffnen Sie Visual Studio.

2. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Projekt Knoten, und wählen Sie **Eigenschaften**aus.

3. Wählen Sie auf der Seite **Eigenschaften** die Registerkarte **Einstellungen** aus.

4. Legen Sie im Einstellungs-Designer den **Namen**, den **Wert**, den **Typ**und den Gültigkeits **Bereich** für die Einstellung fest. Jede Zeile stellt eine einzelne Einstellung dar.

## <a name="see-also"></a>Siehe auch

- [Verwenden von Anwendungseinstellungen und Benutzereinstellungen](using-application-settings-and-user-settings.md)
- [Übersicht über Anwendungseinstellungen](application-settings-overview.md)
- [Vorgehensweise: Ändern des Werts einer vorhandenen Einstellung zur Entwurfszeit](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
