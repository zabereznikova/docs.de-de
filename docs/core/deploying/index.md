---
title: .NET Core Anwendungsbereitstellung
description: Erfahren Sie mehr über die Möglichkeiten zum Bereitstellen einer .NET Core-Anwendung.
ms.date: 12/03/2018
ms.openlocfilehash: 41c5285f2a9ddf38e4be7326bd5cba1c58370fe7
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740810"
---
# <a name="net-core-application-deployment"></a>.NET Core Anwendungsbereitstellung

Sie können drei Arten von Bereitstellungen für .NET Core-Anwendungen erstellen:

- Framework-abhängige Bereitstellung. Wie der Name schon sagt, benötigt eine Framework-abhängige Bereitstellung (Framework-Dependent Deployment, FDD) eine gemeinsame systemweite Version von .NET Core auf dem Zielsystem. Da .NET Core bereits vorhanden ist, ist Ihre Anwendung auch zwischen .NET Core-Installationen übertragbar. Ihre Anwendung enthält nur ihren eigenen Code und Drittanbieter-Abhängigkeiten, die außerhalb von .NET Core-Bibliotheken bestehen. FDDs enthalten *DLL*-Dateien, die mithilfe des [dotnet-Hilfsprogramms](../tools/dotnet.md) über die Befehlszeile gestartet werden können. `dotnet app.dll` führt z.B. eine Anwendung namens `app` aus.

- Eigenständige Bereitstellung. Im Gegensatz zu FDD müssen bei einer eigenständigen Bereitstellung (Self-Contained Deployment, SCD) die freigegebenen Komponenten nicht auf dem Zielsystem vorhanden sein. Alle Komponenten, einschließlich .NET Core-Bibliotheken und .NET Core Runtime, sind in der Anwendung enthalten und von anderen .NET Core-Anwendungen isoliert. SCDs enthalten eine ausführbare Datei (z.B. *app.exe* auf Windows-Plattformen für eine Anwendung namens `app`), die eine umbenannte Version des plattformspezifischen .NET Core-Hosts darstellt, und eine *DLL*-Datei (z.B. *app.dll*), bei der es sich um die eigentliche Anwendung handelt.

- Framework-abhängige ausführbare Dateien. Hierbei wird eine ausführbare Datei erzeugt, die auf einer Zielplattform ausgeführt wird. Ähnlich wie die FDDs sind Framework-abhängige ausführbare Dateien (Framework-Dependent Executables, FDEs) plattformspezifisch und stellen keine eigenständige Bereitstellung dar. Diese Bereitstellungen hängen zur Ausführung weiterhin von dem Vorhandensein einer systemweiten Version von .NET Core ab. Im Gegensatz zu einer SCD enthält Ihre App nur ihren eigenen Code und Drittanbieterabhängigkeiten, die außerhalb der .NET Core-Bibliotheken vorliegen. FDEs erzeugen eine ausführbare Datei, die auf der Zielplattform ausgeführt wird.

## <a name="framework-dependent-deployments-fdd"></a>Framework-abhängige Bereitstellungen (FDD)

Für eine FDD stellen Sie nur Ihre Anwendungen und Drittanbieter-Abhängigkeiten bereit. Ihre App verwendet die .NET Core- Version, die auf dem Zielsystem vorhanden ist. Dies ist das Standardbereitstellungsmodell für .NET Core- und ASP.NET Core-Apps, die für .NET Core vorgesehen sind.

### <a name="why-create-a-framework-dependent-deployment"></a>Warum eine Framework-abhängige Bereitstellung erstellen?

Die Bereitstellung einer FDD hat eine Reihe von Vorteilen:

- Sie müssen die Zielbetriebssysteme, auf denen Ihre .NET Core-Anwendung ausgeführt wird, nicht im Voraus definieren. Da .NET Core unabhängig vom Betriebssystem ein gemeinsames PE-Dateiformat für ausführbare Dateien verwendet, kann .NET Core Ihrer Anwendung unabhängig vom zugrunde liegenden Betriebssystem ausführen. Weitere Informationen zum PE-Dateiformat finden Sie unter [.NET Assembly-Dateiformat](../../standard/assembly/file-format.md).

- Ihr Bereitstellungspaket ist klein. Sie müssen nur Ihre Anwendung und deren Abhängigkeiten bereitstellen, nicht .NET Core selbst.

- Sofern keine Außerkraftsetzung durchgeführt wird, verwenden FDDs die neueste gewartete Runtime, die auf dem Zielsystem installiert ist. Auf diese Weise kann Ihre Anwendung die aktuelle gepatchte Version der .NET Core-Runtime nutzen. 

- Mehrere Anwendungen verwenden die gleiche .NET Core-Installation, die Speicherplatz und Arbeitsspeicher auf dem Hostsystem verringert.

Es gibt auch einige Nachteile:

- Ihre App kann nur ausgeführt werden, wenn die anvisierte .NET Core-Version [oder eine höhere Version](../versions/selection.md#framework-dependent-apps-roll-forward) bereits auf dem Hostsystem installiert ist.

- Es ist möglich, dass die .NET Core Runtime und die Bibliotheken ohne Ihr Wissen in zukünftigen Versionen geändert werden. In seltenen Fällen kann dies das Verhalten Ihrer Anwendung ändern.

## <a name="self-contained-deployments-scd"></a>Eigenständige Bereitstellungen (Self-contained deployments, SCD)

Bei einer eigenständigen Bereitstellung stellen Sie nicht nur Ihre Anwendung und alle erforderlichen Drittanbieterabhängigkeiten bereit, sondern auch die .NET Core-Version, mit der Sie Ihre Anwendung erstellt haben. Eine eigenständige Bereitstellung schließt allerdings nicht die [nativen Abhängigkeiten von .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) auf verschiedenen Plattformen mit ein. Diese müssen daher vor dem Ausführen der Anwendung installiert werden. Weitere Informationen zur Versionsbindung zur Laufzeit finden Sie im Artikel zur [Versionsbindung in .NET Core](../versions/selection.md).

Ab NET Core 2.1 SDK (Version 2.1.300) unterstützt .NET Core das *Rollforward von Patchversionen*. Bei Erstellung einer eigenständigen Bereitstellung enthalten .NET Core-Tools automatisch die neueste gewartete Runtime der .NET Core-Version, auf die die Anwendung ausgerichtet ist. (Die neueste gewartete Runtime enthält Sicherheitspatches und andere Fehlerbehebungen.) Die gewartete Runtime muss auf Ihrem Buildsystem nicht vorhanden sein; sie wird automatisch von NuGet.org heruntergeladen. Weitere Informationen, einschließlich Anweisungen zum Deaktivieren des Rollforwards von Patchversionen, finden Sie unter [Rollforward der eigenständigen Runtimebereitstellung](runtime-patch-selection.md).

Framework-abhängige Bereitstellungen (FDD) und eigenständige Bereitstellungen (SCD) verwenden getrennte ausführbare Hostdateien, sodass Sie eine ausführbare Hostdatei für eine SCD mit Ihrer Herausgebersignatur signieren können.

### <a name="why-deploy-a-self-contained-deployment"></a>Was spricht für eine eigenständige Bereitstellung?

Das Bereitstellen einer eigenständigen Bereitstellung hat zwei wesentliche Vorteile:

- Sie haben die alleinige Kontrolle über die .NET Core-Version, die mit Ihrer Anwendung bereitgestellt wird. .NET Core kann nur von Ihnen bearbeitet werden.

- Sie können sicher sein, dass das Zielsystem Ihre .NET Core-Anwendung ausführen kann, da Sie die .NET Core-Version bereitstellen, die darauf ausgeführt werden soll.

Es hat auch einige Nachteile:

- Da .NET Core in Ihrem Bereitstellungspaket enthalten ist, müssen Sie die Zielplattformen auswählen, für die Sie im Voraus Bereitstellungspaketen erstellen.

- Die Größe Ihres Bereitstellungspakets ist relativ groß, da es auch .NET Core, Ihre Anwendung und ihre Drittanbieter-Abhängigkeiten enthält.

  Ab .NET Core 2.0 können Sie die Größe Ihrer Bereitstellung auf Linux-Systemen um etwa 28 MB reduzieren, indem Sie den [*invarianten Globalisierungsmodus*](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md) von .NET Core verwenden. Normalerweise basiert die Globalisierungsunterstützung von .NET Core unter Linux auf den [ICU-Bibliotheken](http://icu-project.org). Im invarianten Modus werden die Bibliotheken nicht in die Bereitstellung einbezogen, und alle Kulturen verhalten sich wie die [invariante Kultur](xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType).

- Das Bereitstellen von zahlreichen eigenständigen .NET Core-Anwendungen auf ein System kann viel Speicherplatz verbrauchen, da jede Anwendung .NET Core-Dateien dupliziert.

## <a name="framework-dependent-executables-fde"></a>Framework-abhängige ausführbare Dateien (FDEs)

Ab .NET Core 2.2 können Sie Ihre App als FDE bereitstellen, gemeinsam mit erforderlichen Drittanbieterabhängigkeiten. Ihre App verwendet die .NET Core- Version, die auf dem Zielsystem installiert ist.

### <a name="why-deploy-a-framework-dependent-executable"></a>Was spricht für eine Framework-abhängige ausführbare Datei?

Die Bereitstellung einer FDE hat eine Reihe von Vorteilen:

- Ihr Bereitstellungspaket ist klein. Sie müssen nur Ihre Anwendung und deren Abhängigkeiten bereitstellen, nicht .NET Core selbst.

- Mehrere Anwendungen verwenden die gleiche .NET Core-Installation, die Speicherplatz und Arbeitsspeicher auf dem Hostsystem verringert.

- Ihre App kann durch Aufrufen der veröffentlichten ausführbaren Datei ausgeführt werden, ohne das Hilfsprogramm `dotnet` direkt aufzurufen.

Es gibt auch einige Nachteile:

- Ihre App kann nur ausgeführt werden, wenn die anvisierte .NET Core-Version [oder eine höhere Version](../versions/selection.md#framework-dependent-apps-roll-forward) bereits auf dem Hostsystem installiert ist.

- Es ist möglich, dass die .NET Core Runtime und die Bibliotheken ohne Ihr Wissen in zukünftigen Versionen geändert werden. In seltenen Fällen kann dies das Verhalten Ihrer Anwendung ändern.

- Sie müssen Ihre App für jede Zielplattform veröffentlichen.

## <a name="step-by-step-examples"></a>Beispiele mit Schrittanleitungen

Beispiele mit Schrittanleitungen für die Bereitstellung von .NET Core-Apps mit Befehlszeilenschnittstellentools finden Sie unter [Deploying .NET Core Apps with CLI Tools](deploy-with-cli.md) (Bereitstellen von .NET Core-Apps mit Befehlszeilenschnittstellentools). Beispiele mit Schrittanleitungen für die Bereitstellung von .NET Core-Apps mit Visual Studio finden Sie unter [Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md) (Bereitstellen von .NET Core-Apps mit Visual Studio). 

## <a name="see-also"></a>Siehe auch

- [Deploying .NET Core Apps with CLI Tools (Bereitstellen von .NET Core-Apps mit Befehlszeilenschnittstellentools)](deploy-with-cli.md)
- [Deploying .NET Core Apps with Visual Studio (Bereitstellen von .NET Core-Apps mit Visual Studio)](deploy-with-vs.md)
- [Pakete, Metapakete und Frameworks](../packages.md)
- [.NET Core Runtime-ID (RID)-Katalog](../rid-catalog.md)
