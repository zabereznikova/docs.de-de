---
title: Debuggen von CLR-Aktivierungsproblemen
ms.date: 03/30/2017
helpviewer_keywords:
- CLR activation, debugging issues
ms.assetid: 4fe17546-d56e-4344-a930-6d8e4a545914
ms.openlocfilehash: 602ee3c88237a902d48339836fbe25f636ae9705
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75716505"
---
# <a name="how-to-debug-clr-activation-issues"></a>Debuggen von CLR-Aktivierungsproblemen

Wenn Sie Probleme beim Ausführen Ihrer Anwendung mit Ihrer korrekten Version der Common Language Runtime (CLR) haben, können Sie CLR-Aktivierungsprotokolle anzeigen und debuggen. Diese Protokolle können sehr nützlich beim Bestimmen der zugrunde liegenden Ursache für Probleme bei der Aktivierung sein, wenn Ihre Anwendung entweder eine andere CLR-Version als erwartet lädt oder die CLR überhaupt nicht lädt. Im Artikel [.NET Framework-Initialisierungsfehler: Verwalten der Benutzerfreundlichkeit](initialization-errors-managing-the-user-experience.md) wird die Vorgehensweise erläutert, wenn keine CLR für eine Anwendung gefunden werden konnte.

Die CLR-Aktivierungsprotokollierung kann systemweit mithilfe des Registrierungsschlüssels HKEY_LOCAL_MACHINE oder einer Systemumgebungsvariable aktiviert werden. Das Protokoll wird generiert bis der Registrierungseintrag oder Umgebungsvariable entfernt wird. Sie können alternativ einen Benutzer oder eine prozessbezogene Umgebungsvariable für die Aktivierung der Protokollierung mit einem anderen Bereich und anderer Dauer verwenden.

CLR-Aktivierungsprotokolle dürfen nicht mit [Assemblybindungsprotokollen](../tools/fuslogvw-exe-assembly-binding-log-viewer.md) verwechselt werden. Bei diesen handelt es sich um einen vollständig anderen Protokolltyp.

## <a name="to-enable-clr-activation-logging"></a>So aktivieren Sie die CLR-Aktivierungsprotokollierung

### <a name="using-the-registry"></a>Verwendung der Registrierung

1. Navigieren Sie im Registrierungs-Editor zum Ordner HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework (auf einem 32-Bit-Computer) oder zu HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework (auf einem 64-Bit-Computer).

2. Fügen Sie einen Zeichenfolgenwert namens `CLRLoadLogDir` hinzu, und legen Sie ihn auf den vollständigen Pfad des vorhandenen Verzeichnisses fest, wo Sie die CLR-Aktivierungsprotokolle speichern möchten.

Die Aktivierungsprotokollierung bleibt aktiviert, bis Sie den Zeichenfolgenwert entfernen.

### <a name="using-an-environment-variable"></a>Verwenden einer Umgebungsvariablenname

- Legen Sie eine `COMPLUS_CLRLoadLogDir`-Zeichenfolgenwert auf eine Zeichenfolge fest, die den vollständigen Pfad des vorhandenen Verzeichnisses darstellt, wo Sie die CLR-Aktivierungsprotokolle speichern möchten.

    So legen Sie die Umgebungsvariable fest, die ihren Bereich bestimmt:

  - Wenn Sie sie auf Systemebene festlegen, ist die Aktivierungsprotokollierung für alle .NET Framework-Anwendungen auf diesem Computer aktiviert, bis die Umgebungsvariable entfernt wird.

  - Wenn Sie sie auf Benutzerebene festlegen, ist die Aktivierungsprotokollierung nur für das aktuellen Benutzerkonto aktiviert. Die Protokollierung wird fortgesetzt, bis die Umgebungsvariable entfernt ist.

  - Wenn Sie sie von innerhalb des Prozesses festlegen, bevor die CLR geladen wird, ist die Aktivierungsprotokollierung so lange aktiviert, bis der Prozess beendet ist.

  - Wenn Sie sie auf eine Eingabeaufforderung festlegen, bevor Sie eine Anwendung ausführen, ist die Aktivierungsprotokollierung für jede Anwendung aktiviert, die von einer Eingabeaufforderung aus ausgeführt wird.

    Um z.B. Aktivierungsprotokolle im Verzeichnis „c:\clrloadlogs“ mit dem Bereich auf Prozessebene zu speichern, öffnen Sie ein Eingabeaufforderungsfenster, und geben Sie Folgendes ein, bevor Sie die Anwendung ausführen:

    ```console
    set COMPLUS_CLRLoadLogDir=c:\clrloadlogs
    ```

## <a name="example"></a>Beispiel

CLR-Aktivierungsprotokolle stellen eine Vielzahl von Daten über die CLR-Aktivierung und die Verwendung der Hosting-APIs der CLR bereit. Der Großteil dieser Daten wird von Microsoft intern benutzt, doch einige Daten können auch für Entwickler nützlich sein, so wie in diesem Artikel beschrieben.

Das Protokoll spiegelt die Reihenfolge wider, in der die Hosting-APIs von CLR aufgerufen wurden. Es sind auch praktische Daten über die Festlegung installierter Runtimes enthalten, die auf dem Computer ermittelt werden. Das Format des CLR-Aktivierungsprotokolls ist selbst nicht dokumentiert, kann jedoch benutzt werden, um Entwicklern zu helfen, die Probleme bei der CLR-Aktivierung lösen müssen.

> [!NOTE]
> Sie können kein Aktivierungsprotokoll öffnen, bis der Prozess, der die CLR verwendet, beendet ist.

> [!NOTE]
> CLR-Aktivierungsprotokolle werden nicht lokalisiert, sondern bleiben immer in Englisch.

Die wichtigste Information im folgenden Beispiel eines Aktivierungsprotokolls ist hervorgehoben und wird nach dem Protokoll beschrieben.

```output
532,205950.367,CLR Loading log for C:\Tests\myapp.exe
532,205950.367,Log started at 4:26:12 PM on 10/6/2011
532,205950.367,-----------------------------------
532,205950.382,FunctionCall: _CorExeMain
532,205950.382,FunctionCall: ClrCreateInstance, Clsid: {2EBCD49A-1B47-4A61-B13A-4A03701E594B}, Iid: {E2190695-77B2-492E-8E14-C4B3A7FDD593}
532,205950.382,MethodCall: ICLRMetaHostPolicy::GetRequestedRuntime. Version: (null), Metahost Policy Flags: 0x168, Binary: (null), Iid: {BD39D1D2-BA2F-486A-89B0-B4B0CB466891}
532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
532,205950.382,Input values for ComputeVersionString follow this line
532,205950.382,-----------------------------------
532,205950.382,Default Application Name: C:\Tests\myapp.exe
532,205950.382,IsLegacyBind is: 0
532,205950.382,IsCapped is 0
532,205950.382,SkuCheckFlags are 0
532,205950.382,ShouldEmulateExeLaunch is 0
532,205950.382,LegacyBindRequired is 0
532,205950.382,-----------------------------------
532,205950.382,Parsing config file: C:\Tests\myapp.exe
532,205950.382,UseLegacyV2RuntimeActivationPolicy is set to 0
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe
532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
532,205950.382,ERROR: Version v2.0.50727 is not present on the machine.
532,205950.398,SEM_FAILCRITICALERRORS is set to 0
532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
532,205950.398,FunctionCall: RealDllMain. Reason: 0
532,205950.398,FunctionCall: OnShimDllMainCalled. Reason: 0
```

- **CLR-Ladeprotokoll** stellt den Pfad zur ausführbaren Datei bereit, die den Prozess zum Laden des verwalteten Codes gestartet hat. Beachten Sie, dass dies ein nativer Host sein kann.

    ```output
    532,205950.367,CLR Loading log for C:\Tests\myapp.exe
    ```

- **Installierte Runtime** ist die Reihe der auf dem Computer installierten CLR-Versionen, die Kandidaten für die Aktivierungsaufforderung sind.

    ```output
    532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0
    ```

- **mit Version erstellt** ist die Version der CLR, die zum Erstellen der Binärdatei verwendet wurde, die einer Methode, z.B. [ICLRMetaHostPolicy::GetRequestedRuntime](../unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md), bereitgestellt wurde.

    ```output
    532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727
    ```

- **Feature-on-Demand-Installation** bezieht sich auf die Aktivierung von .NET Framework 3.5 unter Windows 8. Im Artikel [.NET Framework-Initialisierungsfehler: Verwalten der Benutzerfreundlichkeit](initialization-errors-managing-the-user-experience.md) finden Sie weitere Informationen zu diesem Szenario.

    ```output
    532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3
    ```

## <a name="see-also"></a>Siehe auch

- [Bereitstellung](index.md)
- [How to: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher](../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
