---
title: Problembehandlung der Meldung „Diese Anwendung konnte nicht gestartet werden“
description: Erfahren Sie, wie vorzugehen ist, wenn das Dialogfeld „Diese Anwendung konnte nicht gestartet werden“ angezeigt wird.
ms.date: 09/05/2019
ms.openlocfilehash: 2140ab38c29d610634f71305c4337c324e0550d8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092049"
---
# <a name="troubleshooting-a-this-application-could-not-be-started-error-message"></a>Problembehandlung der Fehlermeldung „Diese Anwendung konnte nicht gestartet werden“

Für Anwendungen, die für .NET Framework entwickelt wurden, ist es in der Regel erforderlich, dass eine bestimmte Version von .NET Framework auf dem System installiert ist. In einigen Fällen können Sie versuchen, eine Anwendung auszuführen, ohne dass eine installierte Version oder die erwartete Version von .NET Framework vorhanden ist. Dies führt häufig zu einem Fehlerdialogfeld wie dem folgenden:

![Diese Anwendung konnte nicht gestartet werden](media/application-not-started/app-could-not-be-started.png)

Dies weist in der Regel auf eine der folgenden Bedingungen hin:

- Eine .NET Framework-Installation auf Ihrem System ist beschädigt.

- Die Version von .NET Framework, die von der Anwendung benötigt wird, konnte nicht erkannt werden.

Gehen Sie folgendermaßen vor, um dieses Problem zu beheben, damit Sie die Anwendung ausführen können:

1. Laden Sie das [Reparaturtool für .NET Framework („NetFxRepairTool.exe“) ](https://www.microsoft.com/download/details.aspx?id=30135) herunter. Das Tool wird automatisch ausgeführt, nachdem der Download abgeschlossen ist.

1. Wenn das Reparaturtool für .NET Framework weitere Aktionen empfiehlt, etwa die in der folgenden Abbildung gezeigten, wählen Sie **Weiter** aus.

   ![Empfohlene Änderungen](media/application-not-started/repair-tool-recommended-changes.png)

1. Das Reparaturtool für .NET Framework zeigt ein Dialogfeld an (siehe Abbildung unten), um anzugeben, dass die Änderungen abgeschlossen wurden. Lassen Sie das Dialogfeld geöffnet, während Sie versuchen, die Anwendung erneut auszuführen. Dies sollte erfolgreich sein, wenn das Reparaturtool für .NET Framework eine beschädigte .NET Framework-Installation identifiziert und korrigiert hat.

   ![Empfohlene Änderungen](media/application-not-started/repair-tool-changes-complete.png)

1. Wenn die Anwendung erfolgreich ausgeführt wird, klicken Sie auf die Schaltfläche **Fertig stellen**. Wählen Sie andernfalls die Schaltfläche **Weiter** aus.

1. Wenn Sie die Schaltfläche **Weiter** ausgewählt haben, zeigt das Reparaturtool für .NET Framework ein Dialogfeld an, das wie das folgende Beispiel aussieht. Wählen Sie die Schaltfläche **Fertig stellen** aus, um Diagnoseinformationen an Microsoft zu senden.

   ![Das Problem kann nicht gelöst werden](media/application-not-started/repair-tool-no-resolution.png)

1. Wenn Sie die Anwendung immer noch nicht ausführen können, installieren Sie die neueste Version von .NET Framework, die von Ihrer Windows-Version unterstützt wird, wie in der folgenden Tabelle gezeigt.

   |Windows-Version|.NET Framework-Installation|
   |---|---|
   |Windows 10 Anniversary Update und höhere Versionen|[.NET Framework 4.8 Runtime](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |Windows 10, Windows 10-Update von November|[.NET Framework 4.6.2](https://www.microsoft.com/download/details.aspx?id=53345)|
   |Windows 8.1|[.NET Framework 4.8 Runtime](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |Windows 8|[.NET Framework 4.6.1](https://www.microsoft.com/download/details.aspx?id=49981)|
   |Windows 7 SP1|[.NET Framework 4.8 Runtime](https://dotnet.microsoft.com/download/dotnet-framework/net48)|
   |Windows Vista SP2|[.NET Framework 4.6](https://www.microsoft.com/download/details.aspx?id=48130)|

   > [!NOTE]
   > .NET Framework 4.8 ist im Windows 10-Update von Mai 2019 vorinstalliert.

1. Versuchen Sie, die Anwendung zu starten.

1. In einigen Fällen wird möglicherweise ein Dialogfeld wie das folgende angezeigt, in dem Sie aufgefordert werden, .NET Framework 3.5 zu installieren. Wählen Sie **Feature herunterladen und installieren** aus, um .NET Framework 3.5 zu installieren, und starten Sie die Anwendung dann erneut.

   ![Das Problem kann nicht gelöst werden](media/application-not-started/install-3-5.png)

## <a name="see-also"></a>Siehe auch

- [Systemanforderungen für .NET Framework](../get-started/system-requirements.md)
- [Leitfaden für die Installation von .NET Framework](index.md)
- [Problembehandlung bei blockierten Installationen und Deinstallationen von .NET Framework](troubleshoot-blocked-installations-and-uninstallations.md)
