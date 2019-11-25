---
title: Bestimmen der installierten .NET Framework-Versionen
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
ms.openlocfilehash: b860aac01780acb67c53e822eff478b78198996b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738187"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Vorgehensweise: Bestimmen der installierten .NET Framework-Versionen

Benutzer können mehrere Versionen von .NET Framework auf einem Computer [installieren](../install/index.md) und ausführen. Wenn Sie eine App entwickeln oder bereitstellen, müssen Sie möglicherweise herausfinden, welche Versionen von .NET Framework auf dem Computer des Benutzers installiert sind.

.NET Framework besteht aus zwei Hauptkomponenten mit separaten Versionen:

- Ein Satz von Assemblys, bei denen es sich um Sammlungen von Typen und Ressourcen handelt, die die Funktionalität Ihre Apps bereitstellen. .NET Framework und Assemblys verwenden die gleiche Versionsnummer.

- Die CLR (Common Language Runtime, CLR), die den Code Ihrer App verwaltet und ausführt. Die CLR wird durch ihre eigene Versionsnummer identifiziert (siehe [Versionen und Abhängigkeiten](versions-and-dependencies.md)).

> [!NOTE]
> Jede neue Version von .NET Framework enthält weiterhin Funktionen aus den früheren Versionen und fügt neue Funktionen hinzu. Sie können mehrere Versionen von .NET Framework gleichzeitig auf einen Computer laden. Somit können Sie .NET Framework installieren, ohne vorherige Versionen deinstallieren zu müssen. Im Allgemeinen sollten Sie keine vorherigen Versionen von .NET Framework deinstallieren, da eine verwendete Anwendung möglicherweise von einer bestimmten Version abhängt und nicht mehr ausgeführt wird, wenn diese Version entfernt wird.
>
> Zwischen der .NET Framework-Version und der CLR-Version besteht ein Unterschied:
>
> - Die .NET Framework-Version basiert auf den Assemblys, die die .NET Framework-Klassenbibliothek bilden. Beispielsweise zählen zu den .NET Framework-Versionen 4.5, 4.6.1 und 4.7.2.
> - Die CLR-Version basiert auf der Runtime, auf der .NET Framework-Anwendungen ausgeführt werden. Eine einzelne CLR-Version unterstützt in der Regel mehrere .NET Framework-Versionen. Die CLR-Version 4.0.30319.*xxxxx* unterstützt zum Beispiel die .NET Framework-Versionen 4 bis 4.5.2, wobei *xxxxx* kleiner ist als 42000. Die CLR-Version 4.0.30319.42000 unterstützt .NET Framework-Versionen ab .NET Framework 4.6.
>
> Weitere Informationen zu Versionen finden Sie unter [.NET Framework-Versionen und -Abhängigkeiten](versions-and-dependencies.md).

Die Registrierung enthält eine Liste der auf einem Computer installierten .NET Framework-Versionen. Sie können die Registrierung entweder mit dem Registrierungs-Editor anzeigen oder mit Code abfragen:

- Suchen von neueren .NET Framework-Versionen (4.5 und höher):

  - [Suchen von .NET Framework-Versionen 4.5 und höher in der Registrierung](#net_b)
  - [Suchen von .NET Framework-Versionen 4.5 und höher mit Code](#net_d)
  - [Überprüfen mit PowerShell, ob eine mindestens erforderliche .NET Framework-Version (4.5 und höher) vorliegt](#ps_a)

- Suchen nach älteren .NET Framework-Versionen (1 bis 4):

  - [Suchen von .NET Framework-Versionen 4.5 und höher in der Registrierung](#net_a)
  - [Suchen von .NET Framework-Versionen 4.5 und höher mit Code](#net_c)

Verwenden Sie ein Tool oder Code, um eine Liste der auf einem Computer installierten CLR-Versionen zu erhalten:

- [Suchen der aktuellen CLR-Version mit „Clrver.exe“](#clr_a)
- [Suchen der aktuellen CLR-Version mit der Environment-Klasse](#clr_b)

Informationen zum Ermitteln der installierten Updates für jede Version von .NET Framework finden Sie unter [ Gewusst wie: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes](how-to-determine-which-net-framework-updates-are-installed.md).

## <a name="find-newer-net-framework-versions-45-and-later"></a>Suchen von neueren .NET Framework-Versionen (4.5 und höher)

Sie können den Registrierungs-Editor verwenden, um Versionsinformationen in der Registrierung zu finden, oder Sie können die Registrierung programmgesteuert abfragen.

<a name="net_b"></a>

### <a name="use-registry-editor"></a>Verwenden des Registrierungs-Editors

1. Wählen Sie im Menü **Start** die Option **Ausführen** aus, geben Sie *regedit* ein, und klicken Sie dann auf **OK**.

     Sie müssen über Administratorrechte verfügen, um regedit ausführen zu können.

2. Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**. Wenn der Unterschlüssel **Full** nicht vorhanden ist, wurde .NET Framework 4.5 oder höher nicht installiert.

    > [!NOTE]
    > Der Ordner **NET Framework Setup** in der Registrierung beginnt *nicht* mit einem Punkt.

3. Suchen Sie nach einem DWORD-Eintrag mit dem Namen **Release**. Wenn dieser vorhanden ist, haben Sie .NET Framework 4.5 oder höher installiert. Der Wert ist ein Releaseschlüssel, der einer bestimmten Version des .NET Framework entspricht. In der folgenden Abbildung weist der Eintrag **Release** beispielsweise den Wert 378389 auf, was dem Releaseschlüssel für .NET Framework 4.5 entspricht.

   ![Registrierungseintrag für .NET Framework 4.5](./media/clr-installdir.png "Registrierungseintrag für .NET Framework 4.5")

Die folgende Tabelle enthält den Wert des **Release**-DWORD für einzelne Betriebssysteme für .NET Framework 4.5 und höhere Versionen.

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|.NET Framework-Version|Wert des Versions-DWORD|
|--------------------------------|-------------|
|.NET Framework 4.5|Alle Windows-Betriebssysteme: 378389|
|.NET Framework 4.5.1|Für Windows 8.1 und Windows Server 2012 R2: 378675<br />Für alle anderen Windows-Betriebssysteme: 378758|
|.NET Framework 4.5.2|Alle Windows-Betriebssysteme: 379893|
|.NET Framework 4.6|Für Windows 10: 393295<br />Für alle anderen Windows-Betriebssysteme: 393297|
|.NET Framework 4.6.1|Für Windows 10 November Update-Systeme: 394254<br />Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10): 394271|
|.NET Framework 4.6.2|Auf Systemen unter Windows 10 Anniversary Update und Windows Server 2016: 394802<br />Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 394806|
|.NET Framework 4.7|Für Windows 10 Creators Update: 460798<br />Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 460805|
|.NET Framework 4.7.1|Für Windows 10 Fall Creators Update und Windows Server Version 1709: 461308<br/>Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 461310|
|.NET Framework 4.7.2|Für Windows 10 April 2018 Update und Windows Server Version 1803: 461808<br/>Für alle anderen Betriebssysteme als Windows 10 April 2018 Update und Windows Server Version 1803: 461814|
|.NET Framework 4.8|Unter Windows 10 Update aus Mai 2019 und Windows 10 Update aus November 2019: 528040<br/>Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 528049|

#### <a name="specific-version"></a>Bestimmte Version

Um festzustellen, ob eine *bestimmte* Version von .NET Framework unter einer bestimmten Version des Windows-Betriebssystems installiert ist, testen Sie, ob der **Release**-DWORD-Wert *gleich* dem in der Tabelle aufgeführten Wert ist. Um beispielsweise festzustellen, ob .NET Framework 4.6 auf einem Windows 10-System vorhanden ist, testen Sie, ob der **Release**-Wert *gleich* 393295 ist.

#### <a name="minimum-version"></a>Mindestversion

Um festzustellen, ob eine *Mindestversion* von .NET Framework vorhanden ist, verwenden Sie den kleinsten **RELEASE**-DWORD-Wert für diese Version aus der Tabelle oben. (Zur einfacheren Handhabung werden die Mindestwerte in der folgenden Tabelle ebenfalls aufgeführt.)

Wenn Ihre Anwendung beispielsweise unter .NET Framework 4.8 oder einer höheren Version ausgeführt wird, testen Sie, ob der **RELEASE**-DWORD-Wert *größer oder gleich* 528040 ist.

|.NET Framework-Version|Minimalwert des Versions-DWORD|
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
|.NET Framework 4.8|528040|

#### <a name="multiple-versions"></a>Mehrere Versionen

Um auf mehrere Versionen zu testen, beginnen Sie mit dem Testen auf einen Wert, der *größer oder gleich* dem kleineren DWORD-Wert für die neueste .NET Framework-Version ist, und vergleichen Sie dann den Wert mit dem kleineren DWORD-Wert für jede nachfolgende frühere Version. Wenn Ihre Anwendung beispielsweise .NET Framework 4.7 oder höher erfordert und Sie die spezifische vorhandene Version von .NET Framework bestimmen möchten, starten Sie mit dem Testen auf einen **RELEASE**-DWORD-Wert, der *größer oder gleich* 461808 ist (der kleinere DWORD-Wert für .NET Framework 4.7.2). Vergleichen Sie dann den **RELEASE**-DWORD-Wert mit dem kleineren Wert für jede spätere .NET Framework-Version.

<a name="net_d"></a>

### <a name="query-the-registry-using-code"></a>Abfragen der Registrierung mithilfe von Code

1. Verwenden Sie die Methoden <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> und <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType>, um auf den Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** in der Windows-Registrierung zuzugreifen.

   Wenn der DWORD-Eintrag **Release** im Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** vorhanden ist, bedeutet dies, dass .NET Framework 4.5 oder eine höhere Version auf einem Computer installiert ist.

2. Überprüfen Sie den Wert des Eintrags **Release**, um die installierte Version zu bestimmen. Suchen Sie einen Wert größer als oder gleich dem Wert, der in der [.NET Framework-Versionstabelle](#version_table) aufgeführt ist, um die Aufwärtskompatibilität zu überprüfen.

Im folgenden Beispiel wird der Wert des Eintrags **Release** in der Registrierung überprüft, um die installierten Versionen von .NET Framework 4.5 und höher zu suchen:

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

In diesem Beispiel wird der empfohlenen Vorgehensweise zur Versionsprüfung gefolgt:

- Es wird überprüft, ob der Wert des Eintrags **Release** *größer als der oder gleich dem* Wert der bekannten Releaseschlüssel ist.

- Es wird beginnend mit der neuesten Version bis hin zur ältesten Version geprüft.

<a name="ps_a"></a>

### <a name="use-powershell-to-check-for-a-minimum-required-version"></a>Verwenden von PowerShell zum Prüfen auf eine mindestens erforderliche Version

Verwenden Sie PowerShell-Befehle, um den Wert des Eintrags **Release** des Unterschlüssels **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** zu überprüfen.

In den folgenden Beispielen wird der Wert des Eintrags **Release** überprüft, um zu bestimmen, ob .NET Framework 4.6.2 oder höher installiert ist. Dieser Code gibt `True` zurück, wenn es installiert ist, und andernfalls `False`.

```PowerShell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

Um nach einer anderen mindestens erforderlichen .NET Framework-Version zu suchen, ersetzen Sie `394802` im Beispiel durch einen Wert aus der [.NET Framework-Versionstabelle](#version_table). Verwenden Sie den kleinsten Wert, der für diese Version angezeigt wird.

## <a name="find-older-net-framework-versions-1-through-4"></a>Suchen nach älteren .NET Framework-Versionen (1 bis 4)

<a name="net_a"></a>

### <a name="use-registry-editor-older-framework-versions"></a>Verwenden des Registrierungs-Editors (ältere Frameworkversionen)

1. Wählen Sie im Menü **Start** die Option **Ausführen** aus, geben Sie *regedit* ein, und klicken Sie dann auf **OK**.

    Sie müssen über Administratorrechte verfügen, um regedit ausführen zu können.

2. Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:

    - Für die .NET Framework-Versionen 1.1 bis 3.5 ist jede installierte Version als Unterschlüssel unter dem Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** aufgeführt. Beispiel: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**. Die Versionsnummer ist als Wert im Eintrag **Version** des Unterschlüssels der Version gespeichert.

    - Bei .NET Framework 4 befindet sich der Eintrag **Version** unter dem Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client**, dem Unterschlüssel **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** oder unter beiden Unterschlüsseln.

    > [!NOTE]
    > Der Ordner **NET Framework Setup** in der Registrierung beginnt nicht mit einem Punkt.

    Die folgende Abbildung zeigt den Unterschlüssel und dessen **Version**-Eintrag für .NET Framework 3.5.

    ![Der Registrierungseintrag für .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 und frühere Versionen")

<a name="net_c"></a>

### <a name="query-the-registry-using-code-older-framework-versions"></a>Abfragen der Registrierung mithilfe von Code (ältere Frameworkversionen)

Verwenden Sie die Klasse <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType>, um in der Windows-Registrierung auf den Unterschlüssel **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** zuzugreifen.

Im folgenden Beispiel werden die installierten .NET Framework-Versionen 1 bis 4 ermittelt:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a>Suchen von CLR-Versionen

<a name="clr_a"></a>

### <a name="use-clrverexe"></a>Verwenden von „Clrver.exe“

Verwenden Sie das [CLR-Versionstool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md), um zu bestimmen, welche Versionen der CLR auf einem Computer installiert sind:

- Geben Sie in einer [Developer-Eingabeaufforderung für Visual Studio](../tools/developer-command-prompt-for-vs.md) `clrver` ein.

    Beispielausgabe:

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a>

### <a name="use-the-environment-class"></a>Verwenden der Environment-Klasse

> [!IMPORTANT]
> Für .NET Framework 4.5 und höhere Versionen sollten Sie zum Erkennen der CLR-Version nicht die Eigenschaft <xref:System.Environment.Version%2A?displayProperty=nameWithType> verwenden. Fragen Sie stattdessen die Registrierung ab wie unter [Suchen von .NET Framework-Versionen 4.5 und höher mit Code](#net_d) beschrieben.

1. Fragen Sie die Eigenschaft <xref:System.Environment.Version?displayProperty=nameWithType> ab, um ein <xref:System.Version>-Objekt abzurufen.

    Das zurückgegebene `System.Version`-Objekt identifiziert die Version der Runtime, die gerade den Code ausführt. Es gibt keine Assemblyversionen oder andere Versionen der Runtime zurück, die möglicherweise auf dem Computer installiert wurden.

    Bei den .NET Framework-Versionen 4, 4.5, 4.5.1 und 4.5.2 hat die Zeichenfolgendarstellung des zurückgegebenen <xref:System.Version>-Objekts das Format 4.0.30319.*xxxxx*, wobei *xxxxx*n kleiner ist als 42000. Bei .NET Framework 4.6 und höheren Versionen weist sie das Format 4.0.30319.42000 auf.

2. Fragen Sie das erhaltene `Version`-Objekt wie folgt ab:

   - Verwenden Sie für den Hauptversionsbezeichner (zum Beispiel *4* für Version 4.0) die Eigenschaft <xref:System.Version.Major%2A?displayProperty=nameWithType>.

   - Verwenden Sie für den Nebenversionsbezeichner (zum Beispiel *0* für Version 4.0) die Eigenschaft <xref:System.Version.Minor%2A?displayProperty=nameWithType>.

   - Verwenden Sie für die gesamte Versionszeichenfolge (zum Beispiel *4.0.30319.18010*) die Methode <xref:System.Version.ToString%2A?displayProperty=nameWithType>. Diese Methode gibt einen einzelnen Wert zurück, der die Version der Runtime widerspiegelt, die den Code ausführt. Sie gibt keine Assemblyversionen oder andere Runtimeversionen zurück, die möglicherweise auf dem Computer installiert sind.

Im folgenden Beispiel wird die Eigenschaft <xref:System.Environment.Version%2A?displayProperty=nameWithType> verwendet, um CLR-Versionsinformationen abzurufen:

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes](how-to-determine-which-net-framework-updates-are-installed.md)
- [Installieren von .NET Framework für Entwickler](../install/guide-for-developers.md)
- [.NET Framework-Versionen und -Abhängigkeiten](versions-and-dependencies.md)
