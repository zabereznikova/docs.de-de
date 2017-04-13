---
title: "Gewusst wie: Konfigurieren einer Anwendung f&#252;r die Unterst&#252;tzung von .NET Framework 4 oder 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 63c6b9a8-0088-4077-9aa3-521ab7290f79
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Konfigurieren einer Anwendung f&#252;r die Unterst&#252;tzung von .NET Framework 4 oder 4.5
Alle Apps, die die Common Language Runtime \(CLR\) hosten, müssen die CLR starten oder *aktivieren*, um verwalteten Code auszuführen.  Normalerweise wird eine .NET Framework\-App in der CLR\-Version ausgeführt, für die sie erstellt wurde, aber Sie können dieses Verhalten für Desktop\-Apps ändern, indem Sie eine Anwendungskonfigurationsdatei \(auch als app.config\-Datei bezeichnet\) verwenden.  Das Standardaktivierungsverhalten für Windows Store\-Apps oder Windows Phone\-Apps kann jedoch nicht mit einer Anwendungskonfigurationsdatei geändert werden.  In diesem Artikel wird beschrieben, wie Sie eine Desktop\-App in einer anderen Version von .NET Framework ausführen, und wie auf die Version 4 oder 4.5 abgezielt werden kann.  
  
 Die Version von .NET Framework, in der eine Anwendung ausgeführt wird, wird in folgender Reihenfolge ermittelt:  
  
-   Konfigurationsdatei.  
  
     Wenn die Anwendungskonfigurationsdatei [\<supportedRuntime\>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)\-Einträge enthält, die mindestens eine .NET Framework\-Version angeben, und eine dieser Versionen auf dem Computer des Benutzers vorhanden ist, wird die Anwendung in dieser Version ausgeführt.  Die Konfigurationsdatei liest [\<supportedRuntime\>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)\-Einträge in der Reihenfolge, in der sie aufgelistet werden, und verwendet die erste aufgeführte .NET Framework\-Version, die auf dem Computer des Benutzers vorhanden ist.  \(Verwenden Sie das [\<requiredRuntime\>\-Element](../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) für Version 1.0.\)  
  
-   Kompilierte Version.  
  
     Wenn keine Konfigurationsdatei vorhanden ist, aber die Version von .NET Framework, für die die App erstellt wurde, auf dem Computer des Benutzers installiert ist, wird die App in dieser Version ausgeführt.  
  
-   Neueste installierte Version.  
  
     Wenn die .NET Framework\-Version, für die die App erstellt wurde, nicht vorhanden ist, und die Version nicht im [\<supportedRuntime\>\-Element](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) der Konfigurationsdatei angegeben ist, wird die App in der neuesten .NET Framework\-Version ausgeführt, die auf dem Computer des Benutzers installiert ist.  
  
     Allerdings werden .NET Framework 1.0\-, 1.1\-, 2.0\-, 3.0\- und 3.5\-Apps nicht automatisch in .NET Framework 4 oder höher ausgeführt, und in einigen Fällen kann der Benutzer eine Fehlermeldung erhalten und aufgefordert werden, .NET Framework 3.5 zu installieren.  Das Aktivierungsverhalten kann auch je nach Betriebssystem des Benutzers unterschiedlich sein, da verschiedene Versionen des Windows\-Systems unterschiedliche Versionen von .NET Framework enthalten.  Wenn Ihre App .NET Framework 3.5 und 4 oder höher unterstützt, wird empfohlen, dies mit mehreren Einträgen in der Konfigurationsdatei kenntlich zu machen, um .NET Framework\-Initialisierungsfehler zu vermeiden.  Weitere Informationen finden Sie unter [Versionen und Abhängigkeiten](../../../docs/framework/migration-guide/versions-and-dependencies.md).  
  
 Sie sollten ggf. auch die .NET Framework 3.5\-Apps so konfigurieren, dass sie unter .NET Framework 4 oder 4.5 ausgeführt werden können, und zwar auch bei Computern, auf denen .NET Framework 3.5 installiert ist, da Sie so von den Leistungsverbesserungen in den Versionen 4 und 4.5 profitieren können.  
  
> [!IMPORTANT]
>  Es wird empfohlen, die Apps immer für jede .NET Framework\-Version zu testen, die die App unterstützen soll.  Weitere Informationen zum Upgrade von Anwendungen zur Unterstützung höherer .NET Framework\-Versionen erhalten Sie unter [Versionskompatibilität](../../../docs/framework/migration-guide/version-compatibility.md).  
  
 Informationen zum Ändern der .NET Framework 1.0\- und 1.1\-Apps für Windows 7 und Windows 8 finden Sie unter [Migrieren von .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).  
  
### So konfigurieren Sie Ihre App für .NET Framework 4 oder 4.5  
  
1.  Suchen Sie die Konfigurationsdatei für das .NET Framework\-Projekt, oder fügen Sie sie hinzu.  Die Konfigurationsdatei für eine App befindet sich im gleichen Verzeichnis wie die App und hat den gleichen Namen wie die App, weist aber eine CONFIG\-Erweiterung auf.  Die Anwendungskonfigurationsdatei für die App "MyExecutable.exe" heißt z. B. "MyExecutable.exe.config".  
  
     Um eine Konfigurationsdatei über die Visual Studio\-Menüleiste hinzuzufügen, wählen Sie **Projekt**, **Neues Element hinzufügen** aus.  Wählen Sie im linken Bereich **Allgemein**, und wählen Sie dann **Konfigurationsdatei** aus.  Nennen Sie die Konfigurationsdatei „*appName*.exe.config“.  Diese Menüelemente sind nicht für Windows Store\-App\- oder Windows Phone\-App\-Projekte verfügbar, da die Aktivierungsrichtlinie auf diesen Plattformen nicht geändert werden kann.  
  
2.  Fügen Sie das [\<supportedRuntime\>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)\-Element wie folgt der Anwendungskonfigurationsdatei hinzu:  
  
    ```  
    <configuration>  
      <startup>  
        <supportedRuntime version="<version>"/>  
      </startup>  
    </configuration>  
  
    ```  
  
     wobei *\<version\>* die CLR\-Version angibt, die der .NET Framework\-Version entspricht, die von Ihrer App unterstützt wird.  Verwenden Sie diese Zeichenfolgen:  
  
    -   .NET Framework 1.0: "v1.0.3705"  
  
    -   .NET Framework 1.1: "v1.1.4322"  
  
    -   .NET Framework 2.0, 3.0 und 3.5: "v2.0.50727"  
  
    -   .NET Framework 4 und 4.5 \(einschließlich Punktversionen wie 4.5.1\): "v4.0"  
  
     Sie können mehrere [\<supportedRuntime\>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)\-Elemente nach Priorität aufgelistet hinzufügen, um Unterstützung für mehrere Versionen von .NET Framework anzugeben.  
  
 Die folgende Tabelle zeigt, wie mit den Einstellungen der Anwendungskonfigurationsdatei und den auf einem Computer installierten .NET Framework\-Versionen die Version ermittelt wird, in der eine .NET Framework 3.5\-App ausgeführt wird.  Die Beispiele beziehen sich konkret auf eine .NET Framework 3.5\-Anwendung, allerdings folgen Zielanwendungen, die mit früheren .NET Framework\-Versionen erstellt werden, der gleichen Logik.  Beachten Sie, dass die .NET Framework 2.0\-Versionsnummer \(v2.0.50727\) verwendet wird, um .NET Framework 3.5 in der Anwendungskonfigurationsdatei anzugeben.  
  
|||||  
|-|-|-|-|  
|App.config\-Dateieinstellung|Auf Computer mit installierter Version 3.5|Auf Computer mit installierten Versionen 3.5 und 4 oder 4.5|Auf Computer mit installierter Version 4 oder 4.5|  
|Keine|Wird unter 3.5 ausgeführt|Wird unter 3.5 ausgeführt|Zeigt eine Fehlermeldung an, in der der Benutzer aufgefordert wird, die richtige Version zu installieren.\*|  
|`<supportedRuntime version="v2.0.50727"/>`|Wird unter 3.5 ausgeführt|Wird unter 3.5 ausgeführt|Zeigt eine Fehlermeldung an, in der der Benutzer aufgefordert wird, die richtige Version zu installieren.\*|  
|`<supportedRuntime version="v2.0.50727"/>`  <br />  `<supportedRuntime version="v4.0"/>`|Wird unter 3.5 ausgeführt|Wird unter 3.5 ausgeführt|Wird unter 4 oder 4.5 ausgeführt|  
|`<supportedRuntime version="v4.0"/>`  <br />  `<supportedRuntime version="v2.0.50727"/>`|Wird unter 3.5 ausgeführt|Wird unter 4 oder 4.5 ausgeführt|Wird unter 4 oder 4.5 ausgeführt|  
|`<supportedRuntime version="v4.0"/>`|Zeigt eine Fehlermeldung an, in der der Benutzer aufgefordert wird, die richtige Version zu installieren.\*|Wird unter 4 oder 4.5 ausgeführt|Wird unter 4 oder 4.5 ausgeführt|  
  
 \* Weitere Informationen zu dieser Fehlermeldung und \-umgehung finden Sie unter [.NET Framework\-Initialisierungsfehler: Verwalten der Benutzerfreundlichkeit](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md).  
  
## Siehe auch  
 [Migrieren von .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)   
 [Migrationshandbuch](../Topic/Migration%20Guide%20to%20the%20.NET%20Framework%204.6%20and%204.5%20.md)