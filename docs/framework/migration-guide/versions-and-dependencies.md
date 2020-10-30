---
title: .NET Framework- und Windows-Betriebssystemversionen
description: Hier erhalten Sie Informationen zu wichtigen Features der einzelnen .NET Framework-Versionen, einschließlich zugrunde liegender CLR-Versionen und vom Windows-Betriebssystem installierter Versionen.
ms.date: 01/17/2020
helpviewer_keywords:
- versions, .NET Framework
ms.assetid: f75a72de-e2f2-4a7a-9574-3f278684ea90
ms.openlocfilehash: f807a9d9a7ccebf2ae71d47e01fbfba7338b1799
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471996"
---
# <a name="net-framework-versions-and-dependencies"></a>.NET Framework-Versionen und -Abhängigkeiten

Jede Version von .NET Framework enthält die CLR (Common Language Runtime) sowie die Basisklassenbibliotheken und andere verwaltete Bibliotheken. In diesem Artikel werden die wesentlichen Features von .NET Framework je nach Version beschrieben, Informationen zu den zugrunde liegenden CLR-Versionen und den zugehörigen Entwicklungsumgebungen bereitgestellt und die Versionen bestimmt, die vom Windows-Betriebssystem installiert werden.

Jede neue Version von .NET Framework fügt neue Features hinzu, wobei jedoch die Features der Vorgängerversionen beibehalten werden.

[!INCLUDE [net-framework-future](../../../includes/net-framework-future.md)]

Die CLR wird durch ihre eigene Versionsnummer identifiziert. Die .NET Framework-Versionsnummer wird mit jeder neuen Version erhöht, ohne dass jeweils die CLR-Version erhöht wird. Beispiel: .NET Framework 4, 4.5. und spätere Versionen enthalten CLR 4. .NET Framework 2.0, 3.0 und 3.5 enthalten hingegen CLR 2.0. (Es gab keine Version 3 der CLR.)

> [!TIP]
>
> - Eine vollständige Liste unterstützter Betriebssysteme finden Sie unter [Systemanforderungen](../get-started/system-requirements.md).
> - Die Installationsprogramme finden Sie unter [Installieren des .NET Framework für Entwickler](../install/guide-for-developers.md).
> - Informationen zum Ermitteln der auf einem Computer installierten .NET Framework-Versionen finden Sie unter [Gewusst wie: Bestimmen der installierten .NET Framework-Versionen](how-to-determine-which-versions-are-installed.md).

## <a name="version-information"></a>Versionsinformationen

Die folgenden Tabellen enthalten eine Zusammenfassung des .NET Framework-Versionsverlaufs und korrelieren die einzelnen Versionen mit Visual Studio, Windows und Windows Server. Visual Studio unterstützt die Festlegung mehrerer Zielversionen, sodass Sie nicht auf die .NET Framework-Version beschränkt sind, die aufgeführt ist.

- Das Häkchensymbol ✔️ kennzeichnet Betriebssystemversionen, unter denen das .NET Framework von vornherein installiert ist.
- Das Pluszeichensymbol ➕ kennzeichnet Betriebssystemversionen, unter denen .NET Framework nicht installiert ist, aber installiert werden kann.
- Der Asterisk * *\** _ kennzeichnet Betriebssystemversionen, unter denen das .NET Framework (vorinstalliert und nicht vorinstalliert) [in der Systemsteuerung](../install/dotnet-35-windows-10.md) oder über den Server-Manager (für Windows Server) aktiviert werden muss.

| | |
| - | - |
| [.NET Framework 4.8](#net-framework-48) | [.NET Framework 4.7.2](#net-framework-472) | [.NET Framework 4.7.1](#net-framework-471) | [.NET Framework 4.7](#net-framework-47) |
| [.NET Framework 4.6.2](#net-framework-462) | [.NET Framework 4.6.1](#net-framework-461) | [.NET Framework 4.6](#net-framework-46) | [.NET Framework 4.5.2](#net-framework-452) |
| [.NET Framework 4.5.1](#net-framework-451) | [.NET Framework 4.5](#net-framework-45) | [.NET Framework 4](#net-framework-4) | [.NET Framework 3.5](#net-framework-35) |
| [.NET Framework 3.0](#net-framework-30) | [.NET Framework 2.0](#net-framework-20) | [.NET Framework 1.1](#net-framework-11) | [.NET Framework 1.0](#net-framework-10) |

### <a name="net-framework-48"></a>.NET Framework 4.8

- [Neue Features](../whats-new/index.md#whats-new-in-net-framework-48)
- [Neuerungen bei der Barrierefreiheit](../whats-new/whats-new-in-accessibility.md#whats-new-in-accessibility-in-net-framework-48)
- [Versionshinweise](https://github.com/Microsoft/dotnet/tree/master/releases/net48/README.md)

|||
|-|-|
|_ *CLR-Version**|4|
|**Windows-Versionen**|✔️ 10-Update vom Mai 2019<br/>➕ 10-Update vom Oktober 2018 (Version 1809)<br/>➕ 10-Update vom April 2018 (Version 1803)<br/>➕ 10 Fall Creators Update (Version 1709)<br/>➕ 10 Creators Update (Version 1703)<br/>➕ 10 Anniversary Update (Version 1607)<br/>➕ 8.1<br/>➕7|
|**Windows Server-Versionen**|➕ Windows Server 2019<br/>➕ Windows Server, Version 1809<br/>➕ Windows Server, Version 1803<br/>➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 SP1|
|**Ermitteln der installierten .NET-Version**|Verwenden Sie das `Release`-DWORD:<br/>- 528040 (Windows 10-Update vom Mai 2019)<br/>- 528049 (alle weiteren Betriebssystemversionen)<br/>(Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-472"></a>.NET Framework 4.7.2

- [Neue Features](../whats-new/index.md#whats-new-in-net-framework-472)
- [Neuerungen bei der Barrierefreiheit](../whats-new/whats-new-in-accessibility.md#whats-new-in-accessibility-in-net-framework-472)
- [Versionshinweise](https://github.com/Microsoft/dotnet/tree/master/releases/net472/README.md)

|||
|-|-|
|**CLR-Version**|4|
|**In Visual Studio-Version enthalten**|2019<sup>1</sup>|
|**Windows-Versionen**|✔️ 10-Update vom Oktober 2018 (Version 1809)<br/>✔️ 10-Update vom April 2018 (Version 1803)<br/>➕ 10 Fall Creators Update (Version 1709)<br/>➕ 10 Creators Update (Version 1703)<br/>➕ 10 Anniversary Update (Version 1607)<br/>➕ 8.1<br/>➕7|
|**Windows Server-Versionen**|✔️ Windows Server 2019<br/>✔️ Windows Server, Version 1809<br/>✔️ Windows Server, Version 1803<br/>➕ Windows Server, Version 1709<br/>➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 SP1|
|**Ermitteln der installierten .NET-Version**|Verwenden Sie das `Release`-DWORD:<br/>- 461814 (Windows 10-Update vom Oktober 2018)<br/>– 461808 (Windows 10-Update vom April 2018 und Windows Server Version 1803)<br/>– 461814 (alle weiteren Betriebssystemversionen)<br/>(Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md))|

<sup>1</sup> Erfordert die Installation der Workloads **.NET-Desktopentwicklung** , **ASP.NET- und Webentwicklung** , **Azure-Entwicklung** , **Office-/SharePoint-Entwicklung** , **Mobile Entwicklung mit .NET** oder **Plattformübergreifende .NET Core-Entwicklung** .

### <a name="net-framework-471"></a>.NET Framework 4.7.1

- [Neue Features](../whats-new/index.md#whats-new-in-net-framework-471)
- [Neuerungen bei der Barrierefreiheit](../whats-new/whats-new-in-accessibility.md#whats-new-in-accessibility-in-net-framework-471)
- [Versionshinweise](https://github.com/Microsoft/dotnet/tree/master/releases/net471/README.md)

|||
|-|-|
|**CLR-Version**|4|
|**Windows-Versionen**|✔️ 10 Fall Creators Update (Version 1709)<br/>➕ 10 Creators Update (Version 1703)<br/>➕ 10 Anniversary Update (Version 1607)<br/>➕ 8.1<br/>➕7|
|**Windows Server-Versionen**|➕ Windows Server, Version 1803<br/>✔️ Windows Server, Version 1709<br/>➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 SP1|
|**Ermitteln der installierten .NET-Version**|Verwenden Sie das `Release`-DWORD:<br/>– 461308 (Windows 10 Creators Update und Windows Server Version 1709)<br/>– 461310 (alle weiteren Betriebssystemversionen)<br/>(Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-47"></a>.NET Framework 4.7

- [Neue Features](../whats-new/index.md#whats-new-in-net-framework-47)
- [Versionshinweise](https://github.com/Microsoft/dotnet/tree/master/releases/net47/README.md)

|||
|-|-|
|**CLR-Version**|4|
|**Windows-Versionen**|✔️ 10 Creators Update (Version 1703)<br/>➕ 10 Anniversary Update (Version 1607)<br/>➕ 8.1<br/>➕7|
|**Windows Server-Versionen**|➕ 2016<br/>➕ 2012 R2<br/>➕ 2012<br/>➕ 2008 R2 SP1|
|**Ermitteln der installierten .NET-Version**|Verwenden Sie das `Release`-DWORD:<br/>– 460798 (Windows 10 Creators Update)<br/>– 460805 (alle anderen Betriebssystemversionen)<br/>(Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-462"></a>.NET Framework 4.6.2

- [Neue Features](../whats-new/index.md#whats-new-in-net-framework-462)
- [Versionshinweise](https://github.com/Microsoft/dotnet/tree/master/releases/net462/README.md)

|||
|-|-|
|**CLR-Version**|4|
|**Windows-Versionen**|✔️ 10 Anniversary Update (Version 1607)<br/>✔️ 10-Update vom November (Version 1511)<br/>➕ 10<br/>➕ 8.1<br />➕ 7|
|**Windows Server-Versionen**|✔️ 2016<br /><br/>➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 SP1|
|**Ermitteln der installierten .NET-Version**|Verwenden Sie das `Release`-DWORD:<br /><br/>– 394802 (Windows 10 Anniversary Update und Windows Server 2016)<br/>– 394806 (alle weiteren Betriebssystemversionen)<br /><br/>(Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-461"></a>.NET Framework 4.6.1

- [Neue Features](../whats-new/index.md#whats-new-in-net-framework-461)
- [Versionshinweise](https://github.com/Microsoft/dotnet/tree/master/releases/net461/README.md)

|||
|-|-|
|**CLR-Version**|4|
|**In Visual Studio-Version enthalten**|2017<sup>1</sup>|
|**Windows-Versionen**|✔️ 10-Update vom November (Version 1511)<br/>➕ 10<br />➕ 8.1<br />➕ 8<br />➕ 7|
|**Windows Server-Versionen**|➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 SP1|
|**Ermitteln der installierten .NET-Version**|Verwenden Sie das `Release`-DWORD:<br /><br/>– 394254 (Windows 10-Update von November)<br />– 394271 (alle weiteren Betriebssystemversionen)<br /><br/>(Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md))|

<sup>1</sup> Erfordert die Installation der Workloads **.NET-Desktopentwicklung** , **ASP.NET- und Webentwicklung** , **Azure-Entwicklung** , **Office-/SharePoint-Entwicklung** , **Mobile Entwicklung mit .NET** oder **Plattformübergreifende .NET Core-Entwicklung** .

### <a name="net-framework-46"></a>.NET Framework 4.6

- [Neue Features](../whats-new/index.md#whats-new-in-net-2015)
- [Versionshinweise](https://github.com/Microsoft/dotnet/tree/master/releases/net46/README.md)

|||
|-|-|
|**CLR-Version**|4|
|**In Visual Studio-Version enthalten**|2015|
|**Windows-Versionen**|✔️ 10<br /><br />➕ 8.1<br />➕ 8<br />➕ 7<br />➕ Vista|
|**Windows Server-Versionen**|➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 SP1<br />➕ 2008 R2 SP1|
|**Ermitteln der installierten .NET-Version**|Verwenden Sie das `Release`-DWORD:<br /><br />– 393295 (Windows 10)<br />– 393297 (alle weiteren Betriebssystemversionen)<br /><br />(Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-452"></a>.NET Framework 4.5.2

- [Neue Features](../whats-new/index.md#whats-new-in-net-framework-452)
- [Versionshinweise](https://github.com/Microsoft/dotnet/tree/master/releases/net452/README.md)

|||
|-|-|
|**CLR-Version**|4|
|**Windows-Versionen**|➕ 8.1<br />➕ 8<br />➕ 7<br />➕ Vista|
|**Windows Server-Versionen**|➕ 2012 R2<br />➕ 2012<br />➕ 2008 R2 SP1<br />➕ 2008 R2 SP1|
|**Ermitteln der installierten .NET-Version**|Verwenden Sie `Release`-DWORD 379893<br /><br />(Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-451"></a>.NET Framework 4.5.1

- [Neue Features](../whats-new/index.md#whats-new-in-net-framework-451)
- [Versionshinweise](https://github.com/Microsoft/dotnet/tree/master/releases/net451/README.md)

|||
|-|-|
|**CLR-Version**|4|
|**In Visual Studio-Version enthalten**|2013|
|**Windows-Versionen**|✔️ 8.1<br /><br />➕ 8<br />➕ 7<br />➕ Vista|
|**Windows Server-Versionen**|✔️ 2012 R2<br /><br />➕ 2012<br />➕ 2008 R2 SP1<br />➕ 2008 R2 SP1|
|**Ermitteln der installierten .NET-Version**|Verwenden Sie das `Release`-DWORD:<br /><br />– 378675 (Windows 8.1)<br />– 378758 (alle sonstigen)<br /><br />(Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-45"></a>.NET Framework 4.5

- [Neue Features](../whats-new/index.md#whats-new-in-net-framework-45)
- [Versionshinweise](https://github.com/Microsoft/dotnet/tree/master/releases/net45/README.md)

|||
|-|-|
|**CLR-Version**|4|
|**In Visual Studio-Version enthalten**|2012|
|**Windows-Versionen**|✔️ 8<br />➕ 7<br />➕ Vista|
|**Windows Server-Versionen**|✔️ 2012<br />➕ 2008 R2 SP1<br />➕ 2008 R2 SP1|
|**Ermitteln der installierten .NET-Version**|Verwenden Sie `Release`-DWORD 378389<br /><br />(Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md))|

### <a name="net-framework-4"></a>.NET Framework 4

[Neue Features](/previous-versions/dotnet/netframework-4.0/ms171868(v=vs.100))

|||
|-|-|
|**CLR-Version**|4|
|**In Visual Studio-Version enthalten**|2010|
|**Windows-Versionen**|➕ 7<br />➕ Vista|
|**Windows Server-Versionen**|➕ 2008 R2 SP1<br />➕ 2008 R2 SP1<br />➕ 2003|
|**Ermitteln der installierten .NET-Version**|Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-35"></a>.NET Framework 3.5

[Neue Features](/previous-versions/visualstudio/visual-studio-2008/ms171868\(v=vs.90\)):

- LINQ
- Ausdrucksbaumstrukturen
- Verbesserte ASP.NET-Unterstützung für die AJAX-Entwicklung
- HashSet-Sammlungen
- DateTimeOffset
- WPF- und WF-Integration
- Peer-to-Peer-Netzwerke
- Add-Ins für Erweiterbarkeit

|||
|-|-|
|**CLR-Version**|2.0|
|**In Visual Studio-Version enthalten**|2008|
|**Windows-Versionen**|✔️ 10\*<br/>✔️ 8.1\*<br />✔️ 8\*<br />✔️ 7<br /><br />➕ Vista|
|**Windows Server-Versionen**|➕ Windows Server, Version 1803\*<br/>➕ Windows Server, Version 1709\*<br/>➕ 2016\*<br/>➕ 2012 R2\*<br />➕ 2012\*<br /><br />✔️2008 R2 SP1\*<br /><br/>➕ 2008 R2 SP1<br />➕ 2003|
|**Ermitteln der installierten .NET-Version**|Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-30"></a>.NET Framework 3.0

[Neue Features](/previous-versions/visualstudio/visual-studio-2008/bb822048(v=vs.90)):

- Windows Presentation Foundation
- Windows Communication Foundation
- Windows Workflow Foundation
- Windows CardSpace

|||
|-|-|
|**CLR-Version**|2.0|
|**Windows-Versionen**|✔️ Vista|
|**Windows Server-Versionen**|✔️ 2008 R2 SP1*<br />✔️ 2008 SP2\*<br /><br />➕ 2003|
|**Ermitteln der installierten .NET-Version**|Weitere Informationen finden Sie in den [Anweisungen](how-to-determine-which-versions-are-installed.md).|

### <a name="net-framework-20"></a>.NET Framework 2.0

[Neue Features](/previous-versions/visualstudio/visual-studio-2008/t357fb32(v=vs.90)):

- Generics
- Debugger: Bearbeiten und Fortfahren
- Verbesserte Skalierbarkeit und Leistung
- ClickOnce-Bereitstellung
- In ASP.NET 2.0 neue Steuerelemente und Unterstützung für eine breite Palette von Browsern
- 64-Bit-Unterstützung

|||
|-|-|
|**CLR-Version**|2.0|
|**In Visual Studio-Version enthalten**|2005|
|**Windows-Versionen**|Nicht zutreffend|
|**Windows Server-Versionen**|✔️ 2008 R2 SP1<br />✔️ 2008 SP2<br />✔️ 2003|
|**Ermitteln der installierten .NET-Version**|Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-11"></a>.NET Framework 1.1

[Neue Features](/previous-versions/visualstudio/visual-studio-2008/h88tthh0(v=vs.90)):

- ASP.NET Mobile-Steuerelemente
- Parallele Ausführung
- IPv6-Unterstützung

|||
|-|-|
|**CLR-Version**|1.1|
|**In Visual Studio-Version enthalten**|2003|
|**Windows-Versionen**|Nicht zutreffend|
|**Windows Server-Versionen**|✔️ 2003|
|**Ermitteln der installierten .NET-Version**|Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md)|

### <a name="net-framework-10"></a>.NET Framework 1.0

|||
|-|-|
|**CLR-Version**|1.0|
|**In Visual Studio-Version enthalten**|Visual Studio .NET|
|**Windows-Versionen**|Nicht zutreffend|
|**Windows Server-Versionen**|Nicht zutreffend|
|**Ermitteln der installierten .NET-Version**|Siehe [Anweisungen](how-to-determine-which-versions-are-installed.md)|

> [!NOTE]
>
> - .NET Framework muss für das Betriebssystem über [die Systemsteuerung (unter Windows) oder den Server-Manager (für Windows Server)](../install/dotnet-35-windows-10.md#enable-the-net-framework-35-in-control-panel) aktiviert werden.
> - Im Allgemeinen sollten Sie keine Versionen von .NET Framework deinstallieren, die auf dem Computer installiert sind, da es sein kann, dass eine verwendete Anwendung von einer bestimmten Version abhängt und nicht mehr funktioniert, wenn diese Version entfernt wird. Sie können auf einem Computer mehrere .NET Framework-Versionen gleichzeitig laden. Das bedeutet, dass Sie .NET Framework installieren können, ohne frühere Versionen deinstallieren zu müssen. Weitere Informationen finden Sie unter [Erste Schritte](../get-started/index.md).

## <a name="remarks-for-version-45-and-later"></a>Hinweise zu Version 4.5 und höher

.NET Framework 4.5 ist ein direktes Update, das NET Framework 4 auf Ihrem Computer ersetzt. Ebenso sind die .NET Framework-Versionen NET Framework 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 und 4.8 direkte Updates für NET Framework 4.5. Direkte Updates bedeutet, dass die dieselbe Runtimeversion verwendet wird, aber die Assemblyversionen aktualisiert werden und neue Typen und Member enthalten sind. Nach dem Installieren eines dieser Updates sollten Ihre .NET Framework 4-, .NET Framework 4.5-, .NET Framework 4.6- oder .NET Framework 4.7-Apps ohne Neukompilierung weiter ausführbar sein. Umgekehrt ist dies jedoch nicht möglich. Es wird davon abgeraten, für höhere Version von .NET Framework konzipierte Apps mit einer früheren Version auszuführen. Beispielsweise sollten Sie eine App, die für .NET Framework 4.6 vorgesehen ist, nicht mit .NET Framework 4.5 ausführen.

Es gelten die folgenden Richtlinien:

- In Visual Studio können Sie .NET Framework 4.5 als Zielframework für ein Projekt auswählen (dies legt die <xref:Microsoft.Build.Tasks.GetReferenceAssemblyPaths.TargetFrameworkMoniker%2A?displayProperty=nameWithType>-Eigenschaft fest), um das Projekt als .NET Framework 4.5-Assembly oder ausführbare Datei zu kompilieren. Diese Assembly oder ausführbare Datei kann dann auf jedem Computer verwendet werden, auf dem .NET Framework 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 oder 4.8 installiert ist.

- In Visual Studio können Sie .NET Framework 4.5.1 als Zielframework für ein Projekt auswählen, um es als .NET Framework 4.5.1-Assembly oder ausführbare Datei zu kompilieren. Führen Sie diese Assembly oder ausführbare Datei nur auf Computern aus, auf denen .NET Framework 4.5.1 oder höher installiert ist. Eine ausführbare Datei mit .NET Framework 4.5.1 als Ziel ist für die Ausführung auf einem Computer blockiert, auf dem nur eine frühere Version von .NET Framework, z. B. .NET Framework 4.5, installiert ist. Der Benutzer wird aufgefordert, .NET Framework 4.5.1 zu installieren. Darüber hinaus sollten die .NET Framework 4.5.1-Assemblys nicht von einer App abgerufen werden, die für eine frühere Version von .NET Framework vorgesehen ist, z. B. .NET Framework 4.5.

  > [!NOTE]
  > .NET Framework 4.5.1 und .NET Framework 4.5 werden hier nur als Beispiele verwendet. Das beschriebene Prinzip gilt für jede App, die für eine höhere Version von .NET Framework als die auf dem System für die App-Ausführung installierte Version vorgesehen ist.

Einige Änderungen in .NET Framework erfordern möglicherweise Änderungen Ihres App-Codes. Informieren Sie sich unter [Anwendungskompatibilität](application-compatibility.md), bevor Sie vorhandene Apps mit .NET Framework 4.5 oder neueren Versionen auszuführen. Weitere Informationen zum Installieren der aktuellen Version finden Sie unter [Installieren von .NET Framework](../install/guide-for-developers.md). Informationen zur Unterstützung für .NET Framework finden Sie unter [.NET Framework Support-Richtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) auf der .NET-Website.

## <a name="remarks-for-older-versions"></a>Hinweise zu älteren Versionen

Die .NET Framework-Versionen 2.0, 3.0 und 3.5 werden mit der gleichen CLR-Version (CLR 2.0) erstellt. Diese Versionen entsprechen aufeinander folgenden Ebenen einer einzelnen Installation. Jede Version wird inkrementell auf den früheren Versionen aufgebaut. Die Versionen 2.0, 3.0 und 3.5 können auf einem Computer nicht parallel ausgeführt werden. Wenn Sie Version 3.5 installieren, rufen Sie automatisch die 2.0- und 3.0-Ebenen und Apps, die für die Versionen 2.0 erstellt wurden, ab, und 3.0 und 3.5 können alle auf Version 3.5 ausgeführt werden. Allerdings wird in .NET Framework 4 der Ebenenansatz nicht mehr aufgegriffen und neuere Releases (.NET Framework 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 und 4.8) stellen nachfolgende Ebenen einer einzelnen Installation dar. Ab .NET Framework 4 können Sie mit prozessinternem parallelem Hosting mehrere Versionen der CLR in einem einzelnen Prozess ausführen. Weitere Informationen finden Sie unter [Assemblys und parallele Ausführung](../../standard/assembly/side-by-side-execution.md).

Wenn die App für die Version 2.0, 3.0 oder 3.5 vorgesehen ist, werden die Benutzer möglicherweise aufgefordert, .NET Framework 3.5 auf einem Computer mit Windows 8, Windows 8.1 oder Windows 10 zu aktivieren, bevor sie diese App ausführen können. Weitere Informationen finden Sie unter [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8 (Installieren von .NET Framework 3.5 unter Windows 10, Windows 8.1 und Windows 8)](../install/dotnet-35-windows-10.md).

## <a name="next-steps"></a>Nächste Schritte

- .NET Framework-Einsteiger erhalten unter [Übersicht](../get-started/overview.md) eine Einführung in die Schlüsselkonzepte und -funktionen.

- Informationen zu neuen Features und Verbesserungen in .NET Framework 4.5 und dessen Punktreleases finden Sie unter [Neuerungen in .NET Framework](../whats-new/index.md).

- Informationen zum Migrieren der App zu einer neueren Version von .NET Framework finden Sie im [Migrationsleitfaden](index.md).

- Informationen zum Bestimmen der auf einem Computer installierten Versionen oder Updates finden Sie unter [Gewusst wie: Bestimmen der installierten .NET Framework-Versionen](how-to-determine-which-versions-are-installed.md) und [Gewusst wie: Bestimmen der installierten .NET Framework-Updates](how-to-determine-which-net-framework-updates-are-installed.md).

## <a name="see-also"></a>Siehe auch

- [Versionskompatibilität](version-compatibility.md)
| [Offizielle .NET Framework-Supportrichtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework)
- [Problembehandlung bei blockierten Installationen und Deinstallationen von .NET Framework](../install/troubleshoot-blocked-installations-and-uninstallations.md)
