---
title: 'Vorgehensweise: Bestimmen der installierten .NET Framework-Versionen'
ms.date: 02/20/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7661b3ebaa8f29d6d3b2adbc56c405c8f0945f3
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584173"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Vorgehensweise: Bestimmen der installierten .NET Framework-Versionen

Benutzer können mehrere Versionen von .NET Framework auf einem Computer installieren und ausführen. Wenn Sie eine App entwickeln oder bereitstellen, müssen Sie möglicherweise herausfinden, welche Versionen von .NET Framework auf dem Computer des Benutzers installiert sind. Beachten Sie, dass .NET Framework aus zwei Hauptkomponenten besteht, deren Versionen separat voneinander sind:  
  
- Ein Satz von Assemblys, bei denen es sich um Sammlungen von Typen und Ressourcen handelt, die die Funktionalität Ihre Apps bereitstellen. .NET Framework und Assemblys verwenden die gleiche Versionsnummer.  
  
- Die CLR (Common Language Runtime, CLR), die den Code Ihrer App verwaltet und ausführt. Die CLR wird durch ihre eigene Versionsnummer identifiziert (siehe [Versionen und Abhängigkeiten](~/docs/framework/migration-guide/versions-and-dependencies.md)).  
  
Sie können die Registrierung öffnen oder in Ihrem Code abfragen, um eine exakte Liste der auf einem Computer installierten Versionen von .NET Framework zu erhalten:  
  
 [Suchen von .NET Framework-Versionen 1 bis 4 in der Registrierung](#net_a)  
 [Suchen von .NET Framework-Versionen 4.5 und höher in der Registrierung](#net_b)  
 [Codegesteuertes Anzeigen der Registrierung (Versionen 1-4)](#net_c)  
 [Codegesteuertes Anzeigen der Registrierung (Version 4.5 und neuer)](#net_d)  
 [Anzeigen der Registrierung mithilfe von PowerShell (Version 4.5 und neuer)](#ps_a)  

 Sie können ein Tool oder Code verwenden, um die CLR-Version zu ermitteln:  
  
 [Verwenden des Clrver-Tools](#clr_a)  
 [Codegesteuertes Abfragen der System.Environment-Klasse](#clr_b)  

> [!NOTE]
> Zwischen der .NET Framework-Version und der Common Language Runtime-Version (CLR) besteht ein Unterschied. Die .NET Framework-Version basiert auf dem Satz von Assemblys, die die .NET Framework-Klassenbibliothek bilden. Beispielsweise zählen zu den .NET Framework-Versionen 4.5, 4.6.1 und 4.7.2. Die CLR-Version basiert auf der Runtime, mit der .NET Framework-Anwendungen ausgeführt werden, und eine einzelne CLR-Version unterstützt in der Regel mehrere .NET Framework-Versionen. CLR-Version 4.30319. *xxxxx* unterstützt die .NET Framework-Versionen 4 bis 4.5.2; CLR-Version 4.30319.42000 unterstützt .NET Framework-Versionen ab .NET Framework 4.6. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Environment.Version?displayProperty=nameWithType>-Eigenschaft.

 Informationen zum Ermitteln der installierten Updates für jede Version von .NET Framework finden Sie unter [ Gewusst wie: Bestimmen der installierten .NET Framework-Updates](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md). Informationen zum Installieren von .NET Framework finden Sie unter [Install the .NET Framework for developers (Installieren von .NET Framework für Entwickler)](../../../docs/framework/install/guide-for-developers.md).  
  
<a name="net_a"></a>   
## <a name="find-net-framework-versions-1-4-in-the-registry"></a>Suchen von .NET Framework-Versionen 1 bis 4 in der Registrierung 
  
1.  Klicken Sie im Menü **Start** auf **Ausführen**.  
  
2.  Im Feld **Öffnen** geben Sie **regedit.exe** ein.  
  
     Sie müssen über Administratorrechte verfügen, um regedit.exe ausführen zu können.  
  
3.  Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel:  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     Für die .NET Framework-Versionen 1.1 bis 3.5 sind die installierten Versionen als Unterschlüssel unter dem `NDP`-Unterschlüssel aufgelistet. Die Versionsnummer ist unter dem Eintrag **Version** des Unterschlüssels der Version gespeichert. 
     
     Für .NET Framework 4 befindet sich der Eintrag **Version** unter dem `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client`-Unterschlüssel, dem `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full`-Unterschlüssel oder unter beiden Unterschlüsseln.

    > [!NOTE]
    > Der Ordner "NET Framework Setup" in der Registrierung beginnt nicht mit einem Punkt.

    Die folgende Abbildung zeigt den Unterschlüssel für .NET Framework 3.5 zusammen mit seinem **Version**-Eintrag.

     ![Der Registrierungseintrag für .NET Framework 3.5.](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET Framework 4 und frühere Versionen")

<a name="net_b"></a> 
## <a name="find-net-framework-versions-45-and-later-in-the-registry"></a>Suchen von .NET Framework-Versionen 4.5 und höher in der Registrierung

1. Klicken Sie im Menü **Start** auf **Ausführen**.

2. Im Feld **Öffnen** geben Sie **regedit.exe** ein.

     Sie müssen über Administratorrechte verfügen, um regedit.exe ausführen zu können.

3. Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     Beachten Sie, dass der Pfad zum `Full`-Unterschlüssel den Unterschlüssel `Net Framework` anstelle von `.NET Framework` enthält.

    > [!NOTE]
    > Wenn der `Full`-Unterschlüssel nicht vorhanden ist, ist .NET Framework 4.5 oder höher nicht installiert.

     Suchen Sie nach einem DWORD-Wert mit dem Namen `Release`. Wenn das `Release`-DWORD vorhanden ist, können Sie davon ausgehen, dass .NET Framework 4.5 oder höher auf dem Computer installiert ist. Der Wert ist ein Releaseschlüssel, der einer bestimmten Version von .NET Framework entspricht. In der folgenden Abbildung hat das `Release`-DWORD beispielsweise den Wert 378.389, was dem Releaseschlüssel für .NET Framework 4.5 entspricht. 

     ![Registrierungseintrag für .NET Framework 4.5](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")

Die folgende Tabelle listet für jede .NET Framework-Version den Mindestwert für das `Release`-DWORD auf. Sie können diese Werte wie folgt verwenden:

- Um zu bestimmen, ob eine Mindestversion von .NET Framework vorhanden ist, testen Sie, ob der in der Registrierung gefundene `Release`-DWORD-Wert *größer als der oder gleich dem* in der Tabelle aufgeführten Wert ist. Wenn Ihre Anwendung z.B. .NET Framework 4.7 oder höher benötigt, würden Sie testen, ob der Mindestwert des Releaseschlüssels 460.798 beträgt.

- Um zu testen, ob mehrere Versionen vorliegen, beginnen Sie mit der neuesten Version von .NET Framework, und testen Sie dann, ob die einzelnen früheren Versionen vorliegen.

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

|.NET Framework-Version|Wert des Versions-DWORD|
|--------------------------------|-------------|
|.NET Framework 4.5|378389|
|.NET Framework 4.5.1|378675|
|.NET Framework 4.5.2|379893|
|.NET Framework 4.6|393295|
|.NET Framework 4.6.1|394254|
|.NET Framework 4.6.2|394802|
|.NET Framework 4.7|460798|
|.NET Framework 4.7.1|461308|
|.NET Framework 4.7.2|461808|

Eine vollständige Tabelle der Releaseschlüssel für das .NET Framework für bestimmte Versionen des Windows-Betriebssystems finden Sie unter [.NET Framework-Releaseschlüssel und Windows-Betriebssystemversionen](release-keys-and-os-versions.md).

<a name="net_c"></a> 
## <a name="find-net-framework-versions-1-4-with-code"></a>Suchen der .NET Framework-Versionen 1 bis 4 mit Code

- Verwenden Sie die <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType>-Klasse für den Zugriff auf den `Software\Microsoft\NET Framework Setup\NDP\`-Unterschlüssel unter dem `HKEY_LOCAL_MACHINE`-Zweig in der Windows-Registrierung.

     Der folgende Code veranschaulicht diese Abfrage beispielhaft.

    > [!NOTE]
    > In diesem Code wird nicht veranschaulicht, wie .NET Framework 4.5 oder höher zu erkennen ist. Zum Erkennen dieser Versionen überprüfen Sie das `Release`-DWORD, wie im vorherigen Abschnitt beschrieben. Informationen zu Code, der .NET Framework 4.5 oder höhere Versionen erkennt, finden Sie im nächsten Abschnitt dieses Artikels.

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

<a name="net_d"></a> 
## <a name="find-net-framework-versions-45-and-later-with-code"></a>Suchen von .NET Framework-Versionen 4.5 und höher mit Code

1. Wenn das `Release`-DWORD im `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`-Schlüssel vorhanden ist, können Sie davon ausgehen, dass .NET Framework 4.5 oder höher auf dem Computer installiert ist. Der Wert des Schlüsselworts gibt die installierte Version an. Um dieses Schlüsselwort zu überprüfen, verwenden Sie die <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType>- und <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType>-Methode, um auf den Unterschlüssel in der Windows-Registrierung zuzugreifen.

2. Überprüfen Sie den Wert des `Release`-Schlüsselworts, um die installierte Version zu bestimmen. Um die Aufwärtskompatibilität zu überprüfen, stellen Sie fest, ob ein Wert vorliegt, der größer als der oder gleich dem Wert ist, der im Abschnitt [Suchen von .NET Framework-Versionen 4.5 und höher in der Registrierung](#net_b) in der Tabelle aufgeführt ist.

Das folgende Beispiel überprüft den `Release`-Wert in der Registrierung, um zu ermitteln, ob .NET Framework 4.5 oder eine höhere Version installiert ist.

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

In diesem Beispiel wird der empfohlenen Vorgehensweise zur Versionsprüfung gefolgt:

- Es überprüft, ob der Wert des `Release`-Eintrags *größer als oder gleich* dem Wert der bekannten Versionsschlüssel ist.

- Es wird beginnend mit der neuesten Version bis hin zur ältesten Version geprüft.

<a name="ps_a"></a> 
## <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a>Überprüfen mit PowerShell, ob eine mindestens erforderliche .NET Framework-Version (4.5 und höher) vorliegt

Das folgende Beispiel überprüft den Wert des Schlüsselworts `Release`, um zu bestimmen, ob .NET Framework 4.6.2 oder höher installiert ist (es wird `True` zurückgegeben, falls es installiert ist, andernfalls `False`).

    ```PowerShell
    # PowerShell 5
    Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' | Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
    ```

    ```PowerShell
    # PowerShell 4
    (Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
    ```

    You can replace `394802` in the previous example with another value from the following table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section to check for a different minimum required .NET Framework version.
  
<a name="clr_a"></a> 
## <a name="find-the-current-clr-version-with-clrverexe"></a>Suchen der aktuellen CLR-Version mit „Clrver.exe“

Verwenden Sie das CLR-Versions-Tool (Clrver.exe), um zu bestimmen, welche Versionen der Common Language Runtime auf einem Computer installiert sind.

Geben Sie in einer Developer-Eingabeaufforderung für Visual Studio `clrver` ein. Dieser Befehl erzeugt eine Ausgabe ähnlich der folgenden:

```console
Versions installed on the machine:
v2.0.50727
v4.0.30319
```

Weitere Informationen über die Verwendung dieses Tools finden Sie unter [Clrver.exe (CLR-Versionstool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).

<a name="clr_b"></a> 
## <a name="find-the-current-clr-version-with-the-environment-class"></a>Suchen der aktuellen CLR-Version mit der Environment-Klasse

Sie können den Wert der <xref:System.Environment.Version?displayProperty=nameWithType>-Eigenschaft abrufen, um ein <xref:System.Version>-Objekt abzurufen, das die Version der Runtime identifiziert, die gerade den Code ausführt. Diese Eigenschaft gibt einen einzelnen Wert zurück, der die Version der Runtime widerspiegelt, die derzeit den Code ausführt. Es werden keine Assemblyversionen oder andere Versionen der Runtime zurückgegeben, die ggf. auf dem Computer installiert wurden. Sie können mit der <xref:System.Version.Major%2A?displayProperty=nameWithType>-Eigenschaft den Hauptversionsbezeichner abrufen (z.B. „4“ für Version 4.0), mit der <xref:System.Version.Minor%2A?displayProperty=nameWithType>-Eigenschaft den Nebenversionsbezeichner (z.B. „0“ für Version 4.0), oder mit der <xref:System.Version.ToString%2A?displayProperty=nameWithType>-Methode die gesamte Versionszeichenfolge (z.B. „4.0.30319.18010“, wie im folgenden Code gezeigt). 

Bei den .NET Framework-Versionen 4, 4.5, 4.5.1 und 4.5.2 gibt die <xref:System.Environment.Version%2A?displayProperty=nameWithType>Eigenschaft ein <xref:System.Version>-Objekt zurück, dessen Zeichenfolgedarstellung die Form `4.0.30319.xxxxx`besitzt. Für .NET Framework 4.6 und höher weist sie die Form `4.0.30319.42000` auf.

> [!IMPORTANT]
> Für .NET Framework 4.5 und höher wird das Verwenden der Eigenschaft <xref:System.Environment.Version%2A?displayProperty=nameWithType> zum Erkennen der Runtimeversion nicht empfohlen. Stattdessen empfehlen wir, dass Sie die Registrierung abfragen, wie im Abschnitt [Ermitteln der .NET Framework-Versionen durch codegesteuertes Abfragen der Registrierung (.NET Framework 4.5 und neuer)](#net_d) weiter oben in diesem Artikel beschrieben.

Das folgende Beispiel verwendet die <xref:System.Environment.Version%2A?displayProperty=nameWithType>-Eigenschaft, um Runtimeversionsinformationen abzurufen:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Bestimmen der installierten .NET Framework-Updates](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)
- [Installieren von .NET Framework für Entwickler](../../../docs/framework/install/guide-for-developers.md)
- [Versionen und Abhängigkeiten](~/docs/framework/migration-guide/versions-and-dependencies.md)
