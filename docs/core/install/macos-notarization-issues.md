---
title: Verwenden der macOS Catalina-Notarisierung
description: In diesem Artikel erfahren Sie, wie Sie Probleme mit der Notarisierung und mit Zertifikaten unter macOS behandeln, wenn Sie die .NET Core-Runtime, das SDK und mit .NET Core erstellte Apps installieren.
author: adegeo
ms.author: adegeo
ms.date: 02/14/2020
ms.openlocfilehash: a7741727ad46216ebd9936515d8af29b6d7049c2
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656526"
---
# <a name="macos-catalina-notarization-and-the-impact-on-net-core-downloads-and-projects"></a>macOS Catalina-Notarisierung und die Auswirkungen auf .NET Core-Downloads und -Projekte

Ab macOS Catalina (Version 10.15) muss jegliche Software notarisiert werden, die nach dem 1. Juni 2019 erstellt wurde und mit einer Entwickler-ID verteilt wird. Diese Voraussetzung gilt für die .NET Core-Runtime, das .NET Core SDK und jegliche Software, die mit .NET Core erstellt wird. In diesem Artikel werden gängige Szenarios beschrieben, die bei .NET Core und der macOS-Notarisierung auftreten können.

## <a name="installing-net-core"></a>Installieren von .NET Core

Die Installationsprogramme für die Versionen 3.1, 3.0 und 2.1 von .NET Core (sowohl für die Runtime als auch das SDK) wurden seit dem 18. Februar 2020 notarisiert. Vorherige Versionen wurden nicht notarisiert. Sie können eine nicht notarisierte Version von .NET Core manuell installieren, indem Sie zunächst das Installationsprogramm herunterladen und dann den Befehl `sudo installer` ausführen. Weitere Informationen finden Sie unter [Herunterladen und manuelles Installieren für macOS](sdk.md?pivots=os-macos#download-and-manually-install).

Ab den folgenden Versionen sind die .NET Core-Installationsprogramme notarisiert:

- .NET Core Runtime
  - 2.1.16
  - 3.0.3
  - 3.1.2

- .NET Core SDK
  - 2.1.512
  - 3.0.103
  - 3.1.102

## <a name="apphost-is-disabled-by-default"></a>appHost ist standardmäßig deaktiviert

Nicht notarisierte Versionen von .NET Core SDK 3.0 und höher erstellen eine native ausführbare Mach-O-Datei (als **appHost** bekannt), sobald ihr Projekt kompiliert, veröffentlicht oder ausgeführt wird. Diese ausführbare Datei ist eine praktische Methode zum Ausführen Ihrer App. Andernfalls muss Ihre App durch Ausführen von `dotnet <filename.dll>` gestartet werden. Wenn die appHost-Datei aktiviert ist, wird der `dotnet run`-Befehl im Kontext der appHost-Datei aufgerufen. Weitere Informationen finden Sie im Abschnitt [Kontext der appHost-Datei](#context-of-the-apphost).

Beginnend mit den notarisierten Versionen des .NET Core SDK 3.0 wird die ausführbare appHost-Datei nicht standardmäßig generiert. Sie können die Generation der appHost-Datei mit der booleschen Einstellung [`UseAppHost`](../project-sdk/msbuild-props.md#useapphost) in der Projektdatei aktivieren. Sie können die appHost-Datei auch mit dem `-p:UseAppHost`-Parameter für den spezifischen `dotnet`-Befehl aktivieren, den Sie über die Befehlszeile ausführen:

- Projektdatei

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- Befehlszeilenparameter

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

Es wird immer eine appHost-Datei erstellt, wenn Sie Ihre App [eigenständig](../deploying/index.md#publish-self-contained) veröffentlichen.

Weitere Informationen über die `UseAppHost`-Einstellung finden Sie unter [MSBuild-Eigenschaften für Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).

### <a name="context-of-the-apphost"></a>Kontext der appHost-Datei

Wenn die appHost-Datei in Ihrem Projekt aktiviert ist, und Sie den `dotnet run`-Befehl zum Ausführen Ihrer App verwenden, wird die App im Kontext der appHost-Datei und nicht im Kontext des Standardhosts aufgerufen (der Standardhost entspricht dem `dotnet`-Befehl). Wenn die appHost-Datei in Ihrem Projekt deaktiviert ist, führt der `dotnet run`-Befehl Ihre App im Kontext des Standardhosts aus. Selbst wenn die appHost-Datei deaktiviert ist, wird eine ausführbare appHost-Datei beim Veröffentlichen Ihrer App als eigenständig generiert. Benutzer verwenden diese ausführbare Datei zum Ausführen Ihrer App. Wenn Sie Ihre App mit `dotnet <filename.dll>` ausführen, wird die App mit dem Standardhost aufgerufen, der Shared Runtime.

Wenn eine App aufgerufen wird, die die appHost-Datei verwendet, unterscheidet sich der Zugriff auf die App vom notarisierten Standardhost. Wenn Ihre App auf Zertifikate zugreifen muss, die über den Standardhost installiert wurden, verwenden Sie den `dotnet run`-Befehl zum Ausführen Ihrer App über die Projektdatei, oder verwenden Sie den `dotnet <filename.dll>`-Befehl, um die App direkt auszuführen.

Weitere Informationen über dieses Szenario finden Sie im Abschnitt [ASP.NET Core, macOS und Zertifikate](#aspnet-core-and-macos-and-certificates).

## <a name="aspnet-core-and-macos-and-certificates"></a>ASP.NET Core, macOS und Zertifikate

.NET Core bietet die Möglichkeit, Zertifikate in der macOS-Keychain mit der <xref:System.Security.Cryptography.X509Certificates>-Klasse zu verwalten. Der Zugriff auf die macOS-Keychain verwendet bei der Entscheidung, welche Partition berücksichtigt werden soll, die Identität der Anwendung als Primärschlüssel. Beispielsweise speichern nicht signierte Anwendungen Geheimnisse in der nicht signierten Partition. Signierte Anwendungen speichern ihre Geheimnisse jedoch in Partitionen, auf die nur sie zugreifen können. Die Ausführungsquelle, die Ihre App aufruft, entscheidet, welche Partition verwendet wird.

.NET Core bietet drei Ausführungsquellen: [appHost](#apphost-is-disabled-by-default), Standardhost (der `dotnet`-Befehl) und einen benutzerdefinierten Host. Alle Ausführungsmodelle können verschiedene signierte oder nicht signierte Identitäten aufweisen und verfügen über Zugriff auf verschiedene Partitionen in der Keychain. Auf Zertifikate, die von einem Modus importiert werden, kann möglicherweise nicht über einen anderen Modus zugegriffen werden. Beispielsweise verfügen die notarisierten Versionen von .NET Core über einen Standardhost, der signiert ist. Zertifikate werden basierend auf ihrer Identität in eine sichere Partition importiert. Der Zugriff auf diese Zertifikate ist nicht über eine generierte appHost-Datei möglich, da diese nicht signiert ist.

Ein weiteres Beispiel besteht darin, dass ASP.NET Core standardmäßig ein Standard-SSL-Zertifikat über den Standardhost importiert. ASP.NET Core-Anwendungen, die eine appHost-Datei verwenden, verfügen über keinen Zugriff auf dieses Zertifikat. Wenn .NET Core ein nicht zugängliches Zertifikat ermittelt, wird ein Fehler ausgelöst. Die Fehlermeldung bietet Anweisungen zum Beheben des Problems.

Wenn die Zertifikatfreigabe erforderlich ist, bietet macOS Konfigurationsoptionen über das Hilfsprogramm `security`.

Weitere Informationen zur Behandlung von ASP.NET Core-Zertifikatproblemen finden Sie unter [Erzwingen von HTTPS in ASP.NET Core](/aspnet/core/security/enforcing-ssl?view=aspnetcore-3.1&tabs=visual-studio#troubleshoot-certificate-problems).

## <a name="default-entitlements"></a>Standardberechtigungen

Der Standardhost von .NET Core (der Befehl `dotnet`) verfügt über einige Standardberechtigungen. Diese Berechtigungen sind für den ordnungsgemäßen Betrieb von .NET Core erforderlich. Manchmal erfordert Ihre Anwendung zusätzliche Berechtigungen. In diesem Fall müssen Sie eine [appHost-Datei](#apphost-is-disabled-by-default) generieren und verwenden und anschließend die erforderlichen Berechtigungen lokal hinzufügen.

Standardberechtigungen für .NET Core:

- `com.apple.security.cs.allow-jit`
- `com.apple.security.cs.allow-unsigned-executable-memory`
- `com.apple.security.cs.allow-dyld-environment-variables`
- `com.apple.security.cs.disable-library-validation`

## <a name="notarize-a-net-core-app"></a>Notarisieren einer .NET Core-App

Wenn Sie Ihre Anwendung unter macOS Catalina (Version 10.15) oder höher ausführen möchten, müssen Sie Ihre App notarisieren. Die appHost-Datei, die Sie mit Ihrer Anwendung zur Notarisierung einreichen, sollte mindestens über die [Standardberechtigungen](#default-entitlements) für .NET Core verfügen.

## <a name="next-steps"></a>Nächste Schritte

- [.NET Core-Abhängigkeiten und -Anforderungen](macos.md#dependencies)
- [Installieren Sie die .NET Core-Runtime und das .NET Core SDK.](macos.md)
