---
title: 'Vorgehensweise: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher'
ms.date: 03/30/2017
helpviewer_keywords:
- configuring apps to support .NET Framework
- .NET Framework, configuring apps
ms.assetid: 63c6b9a8-0088-4077-9aa3-521ab7290f79
ms.openlocfilehash: 586f39fc9b50dcd45bb959ebd0063e3c38d9c3ed
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716246"
---
# <a name="how-to-configure-an-app-to-support-net-framework-4-or-later-versions"></a>Vorgehensweise: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher

Alle Apps, die die Common Language Runtime (CLR) hosten, müssen die CLR starten oder *aktivieren*, um verwalteten Code auszuführen. Normalerweise wird eine .NET Framework-App in der CLR-Version ausgeführt, für die sie erstellt wurde, aber Sie können dieses Verhalten für Desktop-Apps ändern, indem Sie eine Anwendungskonfigurationsdatei (auch als app.config-Datei bezeichnet) verwenden. Das Standardaktivierungsverhalten für Windows Store-Apps oder Windows Phone-Apps kann jedoch nicht mit einer Anwendungskonfigurationsdatei geändert werden. In diesem Artikel wird beschrieben, wie Sie eine Desktop-App in einer anderen Version von .NET Framework ausführen, und wie auf die Version 4 oder höher abgezielt werden kann.

 Die Version von .NET Framework, in der eine Anwendung ausgeführt wird, wird in folgender Reihenfolge ermittelt:

- Konfigurationsdatei.

     Wenn die Anwendungskonfigurationsdatei [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md)-Einträge enthält, die mindestens eine .NET Framework-Version angeben, und eine dieser Versionen auf dem Computer des Benutzers vorhanden ist, wird die Anwendung in dieser Version ausgeführt. Die Konfigurationsdatei liest [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md)-Einträge in der Reihenfolge, in der sie aufgelistet werden, und verwendet die erste aufgeführte .NET Framework-Version, die auf dem Computer des Benutzers vorhanden ist. (Verwenden Sie das [\<requiredRuntime>-Element](../configure-apps/file-schema/startup/requiredruntime-element.md) für Version 1.0.)

- Kompilierte Version.

     Wenn keine Konfigurationsdatei vorhanden ist, aber die Version von .NET Framework, für die die App erstellt wurde, auf dem Computer des Benutzers installiert ist, wird die App in dieser Version ausgeführt.

- Neueste installierte Version.

     Wenn die .NET Framework-Version, für die die App erstellt wurde, nicht vorhanden ist, und die Version nicht im [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md)-Element der Konfigurationsdatei angegeben ist, wird die App in der neuesten .NET Framework-Version ausgeführt, die auf dem Computer des Benutzers installiert ist.

     Allerdings werden .NET Framework 1.0-, 1.1-, 2.0-, 3.0- und 3.5-Apps nicht automatisch in .NET Framework 4 oder höher ausgeführt, und in einigen Fällen kann der Benutzer eine Fehlermeldung erhalten und aufgefordert werden, .NET Framework 3.5 zu installieren. Das Aktivierungsverhalten kann auch je nach Betriebssystem des Benutzers unterschiedlich sein, da verschiedene Versionen des Windows-Systems unterschiedliche Versionen von .NET Framework enthalten. Wenn Ihre App .NET Framework 3.5 und 4 oder höher unterstützt, wird empfohlen, dies mit mehreren Einträgen in der Konfigurationsdatei kenntlich zu machen, um .NET Framework-Initialisierungsfehler zu vermeiden. Weitere Informationen finden Sie unter [Versionen und Abhängigkeiten](versions-and-dependencies.md).

 Sie sollten ggf. auch die .NET Framework 3.5-Apps so konfigurieren, dass sie unter .NET Framework 4 oder höher ausgeführt werden können, und zwar auch bei Computern, auf denen .NET Framework 3.5 installiert ist, da Sie so von den Leistungsverbesserungen in den Versionen 4 und höher profitieren können.

> [!IMPORTANT]
> Es wird empfohlen, die Apps immer für jede .NET Framework-Version zu testen, die die App unterstützen soll. Weitere Informationen zum Upgrade von Anwendungen zur Unterstützung höherer .NET Framework-Versionen erhalten Sie unter [Versionskompatibilität](version-compatibility.md).

 Informationen zum Ändern der .NET Framework 1.0- und 1.1-Apps für Windows 7 und Windows 8 finden Sie unter [Migrieren von .NET Framework 1.1](migrating-from-the-net-framework-1-1.md).

## <a name="to-configure-your-app-to-run-on-the-net-framework-4-or-later-versions"></a>So konfigurieren Sie Ihre App für .NET Framework 4 oder höher

1. Suchen Sie die Konfigurationsdatei für das .NET Framework-Projekt, oder fügen Sie sie hinzu. Die Konfigurationsdatei für eine App befindet sich im gleichen Verzeichnis wie die App und hat den gleichen Namen wie die App, weist aber eine CONFIG-Erweiterung auf. Die Anwendungskonfigurationsdatei für die App "MyExecutable.exe" heißt z. B. "MyExecutable.exe.config".

     Um eine Konfigurationsdatei über die Visual Studio-Menüleiste hinzuzufügen, wählen Sie **Projekt**, **Neues Element hinzufügen** aus. Wählen Sie im linken Bereich **Allgemein**, und wählen Sie dann **Konfigurationsdatei** aus. Benennen Sie die Konfigurationsdatei „*appName*.exe.config“. Diese Menüelemente sind nicht für Windows Store-App- oder Windows Phone-App-Projekte verfügbar, da die Aktivierungsrichtlinie auf diesen Plattformen nicht geändert werden kann.

2. Fügen Sie das [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md)-Element der Anwendungskonfigurationsdatei wie folgt hinzu:

    ```xml
    <configuration>
      <startup>
        <supportedRuntime version="<version>"/>
      </startup>
    </configuration>
    ```

     wobei *\<version>* die CLR-Version angibt, die der .NET Framework-Version entspricht, die von Ihrer App unterstützt wird. Verwenden Sie diese Zeichenfolgen:

    - .NET Framework 1.0: "v1.0.3705"

    - .NET Framework 1.1: "v1.1.4322"

    - .NET Framework 2.0, 3.0 und 3.5: "v2.0.50727"

    - .NET Framework 4 und höhere Versionen: „v4.0“

     Sie können mehrere [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md)-Elemente nach Priorität aufgelistet hinzufügen, um Unterstützung für mehrere Versionen von .NET Framework anzugeben.

 Die folgende Tabelle zeigt, wie mit den Einstellungen der Anwendungskonfigurationsdatei und den auf einem Computer installierten .NET Framework-Versionen die Version ermittelt wird, in der eine .NET Framework 3.5-App ausgeführt wird. Die Beispiele beziehen sich konkret auf eine .NET Framework 3.5-Anwendung, allerdings folgen Zielanwendungen, die mit früheren .NET Framework-Versionen erstellt werden, der gleichen Logik. Beachten Sie, dass die .NET Framework 2.0-Versionsnummer (v2.0.50727) verwendet wird, um .NET Framework 3.5 in der Anwendungskonfigurationsdatei anzugeben.

|App.config-Dateieinstellung|Auf Computer mit installierter Version 3.5|Auf Computer mit installierter Version 3.5, 4 oder höher|Auf Computer mit installierter Version 4 oder höher|
|-|-|-|-|
|Keine|Wird unter 3.5 ausgeführt|Wird unter 3.5 ausgeführt|Zeigt eine Fehlermeldung an, in der der Benutzer aufgefordert wird, die richtige Version zu installieren.*|
|`<supportedRuntime version="v2.0.50727"/>`|Wird unter 3.5 ausgeführt|Wird unter 3.5 ausgeführt|Zeigt eine Fehlermeldung an, in der der Benutzer aufgefordert wird, die richtige Version zu installieren.*|
|`<supportedRuntime version="v2.0.50727"/>` <br /> `<supportedRuntime version="v4.0"/>`|Wird unter 3.5 ausgeführt|Wird unter 3.5 ausgeführt|Kann auf Version 4 oder höher ausgeführt werden|
|`<supportedRuntime version="v4.0"/>` <br /> `<supportedRuntime version="v2.0.50727"/>`|Wird unter 3.5 ausgeführt|Kann auf Version 4 oder höher ausgeführt werden|Kann auf Version 4 oder höher ausgeführt werden|
|`<supportedRuntime version="v4.0"/>`|Zeigt eine Fehlermeldung an, in der der Benutzer aufgefordert wird, die richtige Version zu installieren.*|Kann auf Version 4 oder höher ausgeführt werden|Kann auf Version 4 oder höher ausgeführt werden|

 \* Weitere Informationen zu dieser Fehlermeldung und Möglichkeiten zu ihrer Vermeidung finden Sie unter [.NET Framework-Initialisierungsfehler: Verwalten der Benutzerfreundlichkeit](../deployment/initialization-errors-managing-the-user-experience.md).

## <a name="see-also"></a>Siehe auch

- [Migrieren von .NET Framework 1.1](migrating-from-the-net-framework-1-1.md)
- [Migrationshandbuch](index.md)
