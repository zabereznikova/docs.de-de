---
title: .NET Core Anwendungsbereitstellung
description: Bereitstellen einer .NET Core-Anwendung.
author: rpetrusha
ms.author: ronpet
ms.date: 09/03/2018
ms.openlocfilehash: 2ef63ebd737739b2c8e671d982c3844135689ab4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891310"
---
# <a name="net-core-application-deployment"></a>.NET Core Anwendungsbereitstellung

Sie können zwei Arten von Bereitstellungen für .NET Core-Anwendungen erstellen:

- Framework-abhängige Bereitstellung. Wie der Name schon sagt, benötigt eine Framework-abhängige Bereitstellung (Framework-Dependent Deployment, FDD) eine gemeinsame systemweite Version von .NET Core auf dem Zielsystem. Da .NET Core bereits vorhanden ist, ist Ihre Anwendung auch zwischen .NET Core-Installationen übertragbar. Ihre Anwendung enthält nur ihren eigenen Code und Drittanbieter-Abhängigkeiten, die außerhalb von .NET Core-Bibliotheken bestehen. FDDs enthalten *DLL*-Dateien, die mithilfe des [dotnet-Hilfsprogramms](../tools/dotnet.md) über die Befehlszeile gestartet werden können. `dotnet app.dll` führt z.B. eine Anwendung namens `app` aus.

- Eigenständige Bereitstellung. Im Gegensatz zu FDD müssen bei einer eigenständigen Bereitstellung (Self-Contained Deployment, SCD) die freigegebenen Komponenten nicht auf dem Zielsystem vorhanden sein. Alle Komponenten, einschließlich .NET Core-Bibliotheken und .NET Core Runtime, sind in der Anwendung enthalten und von anderen .NET Core-Anwendungen isoliert. SCDs enthalten eine ausführbare Datei (z.B. *app.exe* auf Windows-Plattformen für eine Anwendung namens `app`), die eine umbenannte Version des plattformspezifischen .NET Core-Hosts darstellt, und eine *DLL*-Datei (z.B. *app.dll*), bei der es sich um die eigentliche Anwendung handelt.

## <a name="framework-dependent-deployments-fdd"></a>Framework-abhängige Bereitstellungen (FDD)

Für eine FDD stellen Sie nur Ihre Anwendungen und Drittanbieter-Abhängigkeiten bereit. Sie müssen .NET Core nicht bereitstellen, da Ihre Anwendung die .NET Core- Version verwendet, die auf dem Zielsystem vorhanden ist. Dies ist das Standardbereitstellungsmodell für .NET Core- und ASP.NET Core-Apps, die für .NET Core vorgesehen sind.

### <a name="why-create-a-framework-dependent-deployment"></a>Warum eine Framework-abhängige Bereitstellung erstellen?

Die Bereitstellung einer FDD hat eine Reihe von Vorteilen:

- Sie müssen die Zielbetriebssysteme, auf denen Ihre .NET Core-Anwendung ausgeführt wird, nicht im Voraus definieren. Da .NET Core unabhängig vom Betriebssystem ein gemeinsames PE-Dateiformat für ausführbare Dateien verwendet, kann .NET Core Ihrer Anwendung unabhängig vom zugrunde liegenden Betriebssystem ausführen. Weitere Informationen zum PE-Dateiformat finden Sie unter [.NET Assembly-Dateiformat](../../standard/assembly-format.md).

- Ihr Bereitstellungspaket ist klein. Sie müssen nur Ihre Anwendung und deren Abhängigkeiten bereitstellen, nicht .NET Core selbst.

- Mehrere Anwendungen verwenden die gleiche .NET Core-Installation, die Speicherplatz und Arbeitsspeicher auf dem Hostsystem verringert.

Es gibt auch einige Nachteile:

- Ihre Anwendung kann nur ausgeführt werden, wenn die .NET Core-Version die Sie anvisieren oder eine höhere Version bereits auf dem Hostsystem installiert ist.

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

  Ab .NET Core 2.0 können Sie die Größe Ihrer Bereitstellung auf Linux-Systemen um etwa 28 MB reduzieren, indem Sie den [*invarianten Globalisierungsmodus*](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md) von .NET Core verwenden. Normalerweise basiert die Globalisierungsunterstützung von .NET Core unter Linux auf den [ICU-Bibliotheken](https://github.com/dotnet/docs/issues/http%22//icu-project.org). Im invarianten Modus werden die Bibliotheken nicht in die Bereitstellung einbezogen, und alle Kulturen verhalten sich wie die [invariante Kultur](xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType).

- Das Bereitstellen von zahlreichen eigenständigen .NET Core-Anwendungen auf ein System kann viel Speicherplatz verbrauchen, da jede Anwendung .NET Core-Dateien dupliziert.

## <a name="step-by-step-examples"></a>Beispiele mit Schrittanleitungen

Beispiele mit Schrittanleitungen für die Bereitstellung von .NET Core-Apps mit Befehlszeilenschnittstellentools finden Sie unter [Deploying .NET Core Apps with CLI Tools](deploy-with-cli.md) (Bereitstellen von .NET Core-Apps mit Befehlszeilenschnittstellentools). Beispiele mit Schrittanleitungen für die Bereitstellung von .NET Core-Apps mit Visual Studio finden Sie unter [Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md) (Bereitstellen von .NET Core-Apps mit Visual Studio). Jedes Thema enthält Beispiele der folgenden Bereitstellungen:

- Framework-abhängige Bereitstellung
- Framework-abhängige Bereitstellung mit Drittanbieterabhängigkeiten
- Eigenständige Bereitstellung
- Eigenständige Bereitstellung mit Drittanbieterabhängigkeiten

## <a name="see-also"></a>Siehe auch

* [Deploying .NET Core Apps with CLI Tools (Bereitstellen von .NET Core-Apps mit Befehlszeilenschnittstellentools)](deploy-with-cli.md)
* [Deploying .NET Core Apps with Visual Studio (Bereitstellen von .NET Core-Apps mit Visual Studio)](deploy-with-vs.md)
* [Pakete, Metapakete und Frameworks](../packages.md)
* [.NET Core Runtime-ID (RID)-Katalog](../rid-catalog.md)
