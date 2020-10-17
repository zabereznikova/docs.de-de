---
title: Bestimmen der installierten .NET Framework-Versionen
description: Verwenden von Code, regedit.exe oder PowerShell, um über eine Abfrage der Windows-Registrierung zu ermitteln, welche .NET Framework-Versionen auf einem Computer installiert sind
ms.date: 02/03/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
ms.openlocfilehash: faeb2c14b9c1d93b558c67a42c223702178407c0
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955589"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>Vorgehensweise: Bestimmen der installierten .NET Framework-Versionen

Benutzer können mehrere Versionen des .NET Frameworks auf einem Computer [installieren](../install/index.md) und ausführen. Wenn Sie eine App entwickeln oder bereitstellen, müssen Sie möglicherweise herausfinden, welche Versionen des .NET Frameworks auf dem Computer des Benutzers installiert sind. Die Registrierung enthält eine Liste der auf einem Computer installierten .NET Framework-Versionen.

Das .NET Framework besteht aus zwei Hauptkomponenten mit separaten Versionen:

- Ein Satz von Assemblys, bei denen es sich um Sammlungen von Typen und Ressourcen handelt, die die Funktionalität Ihre Apps bereitstellen. .NET Framework und Assemblys verwenden die gleiche Versionsnummer. Beispielsweise zählen zu den .NET Framework-Versionen 4.5, 4.6.1 und 4.7.2.

- Die CLR (Common Language Runtime, CLR), die den Code Ihrer App verwaltet und ausführt. Eine einzelne CLR-Version unterstützt in der Regel mehrere .NET Framework-Versionen. Beispiel: Die Version 4.0.30319.*xxxxx* der CLR (wobei *xxxxx* kleiner als 42000 ist) unterstützt die Versionen 4 bis 4.5.2 des .NET Frameworks. Ab Version 4.0.30319.42000 unterstützt die CLR Version 4.6 und höher des .NET Frameworks.

Mithilfe von Tools, die von der Community verwaltet werden, können Sie ermittelt, welche .NET Framework-Versionen installiert sind:

- [https://github.com/jmalarcon/DotNetVersions](https://github.com/jmalarcon/DotNetVersions)

  Ein Befehlszeilentool für .NET 2.0

- [https://github.com/EliteLoser/DotNetVersionLister](https://github.com/EliteLoser/DotNetVersionLister)

  Ein Modul für PowerShell 2.0

Informationen zum Ermitteln der installierten Updates für jede Version des .NET Frameworks finden Sie unter [Vorgehensweise: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes](how-to-determine-which-net-framework-updates-are-installed.md).

## <a name="detect-net-framework-45-and-later-versions"></a>Erkennen von .NET Framework 4.5 und höheren Versionen

Die Version des .NET Frameworks (4.5 und höher), die auf einem Computer installiert ist, wird in der Registrierung unter **HKEY_LOCAL_MACHINE\\Software\\Microsoft\\NET Framework Setup\\NDP\\V4\\Full** aufgeführt. Wenn der Unterschlüssel **Full** fehlt, ist weder .NET Framework 4.5 noch eine höhere Version installiert.

> [!NOTE]
> Der Unterschlüssel **NET Framework Setup** im Registrierungspfad beginnt *nicht* mit einem Punkt.

Der **Release**-Wert REG_DWORD in der Registrierung steht für die installierte .NET Framework-Version.

<a name="version_table"></a>

| .NET Framework-Version | **Release**-Wert |
| ---------------------- | -------------------------- |
| .NET Framework 4.5     | Alle Windows-Betriebssysteme: 378389 |
| .NET Framework 4.5.1   | Für Windows 8.1 und Windows Server 2012 R2: 378675<br />Für alle anderen Windows-Betriebssysteme: 378758 |
| .NET Framework 4.5.2   | Alle Windows-Betriebssysteme: 379893 |
| .NET Framework 4.6     | Für Windows 10: 393295<br />Für alle anderen Windows-Betriebssysteme: 393297 |
| .NET Framework 4.6.1   | Für Windows 10 November Update-Systeme: 394254<br />Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10): 394271 |
| .NET Framework 4.6.2   | Auf Systemen unter Windows 10 Anniversary Update und Windows Server 2016: 394802<br />Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 394806 |
| .NET Framework 4.7     | Für Windows 10 Creators Update: 460798<br />Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 460805 |
| .NET Framework 4.7.1   | Für Windows 10 Fall Creators Update und Windows Server Version 1709: 461308<br/>Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 461310 |
| .NET Framework 4.7.2   | Für Windows 10 April 2018 Update und Windows Server Version 1803: 461808<br/>Für alle anderen Betriebssysteme als Windows 10 April 2018 Update und Windows Server Version 1803: 461814 |
| .NET Framework 4.8     | Unter Windows 10 Update aus Mai 2019 und Windows 10 Update aus November 2019: 528040<br/>Für Windows 10-Update von Mai 2020: 528372<br/>Für alle anderen Windows-Betriebssysteme (einschließlich Windows 10-Betriebssysteme): 528049 |

### <a name="minimum-version"></a>Mindestversion

Sie können ermitteln, ob eine *Mindestversion* des .NET Frameworks vorhanden ist, indem Sie den kleinsten **Release**-Wert für REG_DWORD für diese Version aus der obigen Tabelle entnehmen.

Wenn Ihre Anwendung beispielsweise unter .NET Framework 4.8 oder einer höheren Version ausgeführt wird, testen Sie, ob der **Release**-Wert für REG_DWORD *größer oder gleich* 528040 ist.

| .NET Framework-Version | Minimalwert |
| ---------------------- | ------------- |
| .NET Framework 4.5     | 378389 |
| .NET Framework 4.5.1   | 378675 |
| .NET Framework 4.5.2   | 379893 |
| .NET Framework 4.6     | 393295 |
| .NET Framework 4.6.1   | 394254 |
| .NET Framework 4.6.2   | 394802 |
| .NET Framework 4.7     | 460798 |
| .NET Framework 4.7.1   | 461308 |
| .NET Framework 4.7.2   | 461808 |
| .NET Framework 4.8     | 528040 |

### <a name="use-registry-editor"></a>Verwenden des Registrierungs-Editors

01. Wählen Sie im Menü **Start** die Option **Ausführen** aus, geben Sie *regedit* ein, und klicken Sie dann auf **OK**.

   (Sie müssen über Administratorrechte verfügen, um regedit ausführen zu können.)

01. Öffnen Sie im Registrierungs-Editor den folgenden Unterschlüssel: **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**. Wenn der Unterschlüssel **Full** nicht vorhanden ist, wurde .NET Framework 4.5 oder höher nicht installiert.

01. Suchen Sie nach einem REG_DWORD-Eintrag mit dem Namen **Release**. Wenn dieser vorhanden ist, haben Sie .NET Framework 4.5 oder höher installiert. Der zugehörige Wert entspricht einer bestimmten Version des .NET Frameworks. In der folgenden Abbildung weist der Eintrag **Release** beispielsweise den Wert 528040 auf, was dem Releaseschlüssel für .NET Framework 4.8 entspricht.

   ![Registrierungseintrag für .NET Framework 4.5](./media/clr-installdir.png )

### <a name="use-powershell-to-check-for-a-minimum-version"></a>Verwenden von PowerShell zum Prüfen auf eine Mindestversion

Verwenden Sie PowerShell-Befehle, um den Wert des Eintrags **Release** des Unterschlüssels **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full** zu überprüfen.

In den folgenden Beispielen wird der Wert des Eintrags **Release** überprüft, um zu bestimmen, ob .NET Framework 4.6.2 oder höher installiert ist. Dieser Code gibt `True` zurück, wenn es installiert ist, und andernfalls `False`.

```powershell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

### <a name="query-the-registry-using-code"></a>Abfragen der Registrierung mithilfe von Code

01. Verwenden Sie die Methoden <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> und <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType>, um auf den Unterschlüssel **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full** in der Windows-Registrierung zuzugreifen.

    > [!IMPORTANT]
    > Wenn die App, die Sie ausführen, für 32 Bit optimiert ist und unter einer 64-Bit-Version von Windows ausgeführt wird, unterscheiden sich die Registrierungspfade von den zuvor aufgeführten. Die 64-Bit-Registrierung ist im Unterschlüssel **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** verfügbar. Der Registrierungsunterschlüssel für .NET Framework 4.5 ist beispielsweise **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**.

01. Überprüfen Sie den **Release**-Wert für REG_DWORD, um die installierte Version zu bestimmen. Suchen Sie einen Wert größer als oder gleich dem Wert, der in der [.NET Framework-Versionstabelle](#version_table) aufgeführt ist, um die Aufwärtskompatibilität zu überprüfen.

Im folgenden Beispiel wird der Wert des Eintrags **Release** in der Registrierung überprüft, um die installierten Versionen von .NET Framework 4.5–4.8 und höher zu suchen:

:::code language="csharp" source="snippets/csharp/versions-installed.cs" id="2":::

:::code language="vb" source="snippets/visual-basic/versions-installed.vb" id="2":::

In diesem Beispiel wird die folgende Ausgabe angezeigt:

```output
.NET Framework Version: 4.6.1
```

In diesem Beispiel wird der empfohlenen Vorgehensweise zur Versionsprüfung gefolgt:

- Es wird überprüft, ob der Wert des Eintrags **Release***größer als der oder gleich dem* Wert der bekannten Releaseschlüssel ist.
- Es wird beginnend mit der neuesten Version bis hin zur ältesten Version geprüft.

## <a name="detect-net-framework-10-through-40"></a>Erkennen der Versionen 1.0 bis 4.0 des .NET Frameworks

Jede Version von .NET Framework zwischen den Versionen 1.1 und 4.0 wird unter **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP** als Unterschlüssel aufgeführt. In der folgenden Tabelle wird der Pfad zu den einzelnen .NET Framework-Versionen aufgelistet. Für die meisten Versionen gibt es einen **Install**-Wert für REG_DWORD von `1`, der angibt, dass die jeweilige Version installiert ist. In diesen Unterschlüsseln gibt es auch einen **Version**-Wert für REG_SZ, der eine Versionszeichenfolge enthält.

> [!NOTE]
> Der Unterschlüssel **NET Framework Setup** im Registrierungspfad beginnt *nicht* mit einem Punkt.

| Framework-Version  | Registrierungsunterschlüssel | Wert |
| ------------------ | --------------- | ----- |
| 1.0                | **HKLM\\Software\\Microsoft\\.NETFramework\\Policy\\v1.0\\3705**     | **Install**-Wert für REG_SZ entspricht `1` |
| 1.1                | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v1.1.4322**   | **Install**-Wert für REG_DWORD entspricht `1` |
| 2.0                | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v2.0.50727**  | **Install**-Wert für REG_DWORD entspricht `1` |
| 3.0                | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v3.0\\Setup** | **InstallSuccess**-Wert für REG_DWORD entspricht `1` |
| 3.5                | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v3.5**        | **Install**-Wert für REG_DWORD entspricht `1` |
| 4.0, Clientprofil | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v4\\Client**  | **Install**-Wert für REG_DWORD entspricht `1` |
| 4.0, vollständiges Profil   | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**    | **Install**-Wert für REG_DWORD entspricht `1` |

> [!IMPORTANT]
> Wenn die App, die Sie ausführen, für 32 Bit optimiert ist und unter einer 64-Bit-Version von Windows ausgeführt wird, unterscheiden sich die Registrierungspfade von den zuvor aufgeführten. Die 64-Bit-Registrierung ist im Unterschlüssel **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** verfügbar. Beispielsweise lautet der Registrierungsunterschlüssel für .NET Framework 3.5 **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v3.5**.

Hinweis: Der Registrierungspfad für den Unterschlüssel für .NET Framework 1.0 unterscheidet sich von dem anderer Registrierungsschlüssel.

### <a name="use-registry-editor-older-framework-versions"></a>Verwenden des Registrierungs-Editors (ältere Frameworkversionen)

01. Wählen Sie im Menü **Start** die Option **Ausführen** aus, geben Sie *regedit* ein, und klicken Sie dann auf **OK**.

    Sie müssen über Administratorrechte verfügen, um regedit ausführen zu können.

01. Öffnen Sie den Unterschlüssel, der der Version entspricht, die Sie überprüfen möchten. Verwenden Sie die Tabelle im Abschnitt [Erkennen der Versionen 1.0 bis 4.0 des .NET Frameworks](#detect-net-framework-10-through-40).

    Die folgende Abbildung zeigt den Unterschlüssel und dessen **Version**-Wert für .NET Framework 3.5.

    ![Der Registrierungseintrag für .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 und frühere Versionen")

### <a name="query-the-registry-using-code-older-framework-versions"></a>Abfragen der Registrierung mithilfe von Code (ältere Frameworkversionen)

Verwenden Sie die Klasse <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType>, um in der Windows-Registrierung auf den Unterschlüssel **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP** zuzugreifen.

> [!IMPORTANT]
> Wenn die App, die Sie ausführen, für 32 Bit optimiert ist und unter einer 64-Bit-Version von Windows ausgeführt wird, unterscheiden sich die Registrierungspfade von den zuvor aufgeführten. Die 64-Bit-Registrierung ist im Unterschlüssel **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** verfügbar. Beispielsweise lautet der Registrierungsunterschlüssel für .NET Framework 3.5 **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v3.5**.

Im folgenden Beispiel werden die installierten .NET Framework-Versionen 1–4 ermittelt:

:::code language="csharp" source="snippets/csharp/versions-installed.cs" id="1":::

:::code language="vb" source="snippets/visual-basic/versions-installed.vb" id="1":::

Die Konsole zeigt eine Ausgabe an, die der folgenden in etwa entspricht:

```output
v2.0.50727  2.0.50727.4927  SP2
v3.0  3.0.30729.4926  SP2
v3.5  3.5.30729.4926  SP1
v4.0
  Client  4.0.0.0
```

## <a name="find-clr-versions"></a>Suchen von CLR-Versionen

Die mit dem für .NET Framework installierte CLR-Version wird separat bestimmt. Es gibt zwei Möglichkeiten, die Version der .NET Framework-CLR zu ermitteln:

- **Das Tool Clrver.exe**

  Verwenden Sie das [CLR-Versionstool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md), um zu ermitteln, welche Versionen der CLR auf einem Computer installiert sind. Öffnen Sie die [Developer-Eingabeaufforderung für Visual Studio](../tools/developer-command-prompt-for-vs.md), und geben Sie `clrver` ein.

  Beispielausgabe:

  ```console
  Versions installed on the machine:
  v2.0.50727
  v4.0.30319
  ```

- **Die Klasse `Environment`**

  > [!IMPORTANT]
  > Für .NET Framework 4.5 und höhere Versionen sollten Sie zum Ermitteln der CLR-Version nicht die Eigenschaft <xref:System.Environment.Version%2A?displayProperty=nameWithType> verwenden. Fragen Sie stattdessen wie im Abschnitt [Erkennen von .NET Framework 4.5 und höheren Versionen](#detect-net-framework-45-and-later-versions) beschrieben die Registrierung ab.

  1. Fragen Sie die Eigenschaft <xref:System.Environment.Version?displayProperty=nameWithType> ab, um ein <xref:System.Version>-Objekt abzurufen.

     Das zurückgegebene `System.Version`-Objekt identifiziert die Version der Runtime, die gerade den Code ausführt. Es gibt keine Assemblyversionen oder andere Versionen der Runtime zurück, die möglicherweise auf dem Computer installiert wurden.

     Bei den .NET Framework-Versionen 4, 4.5, 4.5.1 und 4.5.2 hat die Zeichenfolgendarstellung des zurückgegebenen <xref:System.Version>-Objekts das Format 4.0.30319.*xxxxx*, wobei *xxxxx* kleiner als 42000 ist. Bei .NET Framework 4.6 und höheren Versionen weist es das Format 4.0.30319.42000 auf.

  1. Fragen Sie das erhaltene **Version**-Objekt wie folgt ab:

     - Verwenden Sie für den Hauptversionsbezeichner (zum Beispiel *4* für Version 4.0) die Eigenschaft <xref:System.Version.Major%2A?displayProperty=nameWithType>.

     - Verwenden Sie für den Nebenversionsbezeichner (zum Beispiel *0* für Version 4.0) die Eigenschaft <xref:System.Version.Minor%2A?displayProperty=nameWithType>.

     - Verwenden Sie für die gesamte Versionszeichenfolge (zum Beispiel *4.0.30319.18010*) die Methode <xref:System.Version.ToString%2A?displayProperty=nameWithType>. Diese Methode gibt einen einzelnen Wert zurück, der die Version der Runtime widerspiegelt, die den Code ausführt. Sie gibt keine Assemblyversionen oder andere Runtimeversionen zurück, die möglicherweise auf dem Computer installiert sind.

  Im folgenden Beispiel wird die Eigenschaft <xref:System.Environment.Version%2A?displayProperty=nameWithType> verwendet, um CLR-Versionsinformationen abzurufen:

  ```csharp
  Console.WriteLine($"Version: {Environment.Version}");
  ```

  ```vb
  Console.WriteLine($"Version: {Environment.Version}")
  ```

  Die Konsole zeigt eine Ausgabe an, die der folgenden in etwa entspricht:

  ```output
  Version: 4.0.30319.18010
  ```

## <a name="see-also"></a>Siehe auch

- [How to: Ermitteln der installierten .NET Framework-Sicherheitsupdates und -Hotfixes](how-to-determine-which-net-framework-updates-are-installed.md)
- [Installieren von .NET Framework für Entwickler](../install/guide-for-developers.md)
- [.NET Framework-Versionen und -Abhängigkeiten](versions-and-dependencies.md)
