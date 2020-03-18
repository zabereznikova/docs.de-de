---
title: Sicheres Speichern von Anwendungsgeheimnissen während der Entwicklung
description: 'Sicherheit in .NET-Microservices und Webanwendungen: Speichern Sie Ihre Anwendungsgeheimnisse wie Kennwörter, Verbindungszeichenfolgen oder API-Schlüssel nicht in der Quellcodeverwaltung, und informieren Sie sich über die Optionen, die Sie in ASP.NET Core verwenden können, insbesondere müssen Sie wissen, wie „Benutzergeheimnisse“ behandelt werden.'
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: 1ef2246746b9165f1564fa7be64ff7eb28eb1d32
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77501796"
---
# <a name="store-application-secrets-safely-during-development"></a>Sicheres Speichern von Anwendungsgeheimnissen während der Entwicklung

Zum Verbinden mit geschützten Ressourcen und anderen Diensten benötigen ASP.NET Core-Anwendungen in der Regel Verbindungszeichenfolgen, Kennwörter oder andere Anmeldeinformationen, die vertrauliche Informationen enthalten. Diese vertraulichen Informationen werden *Geheimnisse* genannt. Es ist eine bewährte Methode, Geheimnisse nicht in den Quellcode einzufügen und auf keinen Fall in der Quellcodeverwaltung zu speichern. Stattdessen sollten Sie das Konfigurationsmodell von ASP.NET Core verwenden, um Geheimnisse aus sichereren Speicherorten zu lesen.

Sie müssen die Geheimnisse für den Zugriff auf Entwicklungs- und Stagingressourcen von denen trennen, die für den Zugriff auf Produktionsressourcen verwendet werden, da verschiedene Personen Zugriff auf diese verschiedenen Geheimnisse benötigen. Beim Speichern von Geheimnissen, die während der Entwicklung genutzt werden, ist es gebräuchlich, diese entweder in Umgebungsvariablen oder mithilfe des Secret Manager-Tools von ASP.NET Core zu speichern. Für eine sicherere Speicherung in Produktionsumgebungen können Microservices Geheimnisse in Azure Key Vault speichern.

## <a name="store-secrets-in-environment-variables"></a>Speichern von Geheimnissen in Umgebungsvariablen

Eine Möglichkeit, um Geheimnisse aus dem Quellcode fernzuhalten, besteht darin, dass Entwickler zeichenfolgenbasierte Geheimnisse als [Umgebungsvariablen](/aspnet/core/security/app-secrets#environment-variables) auf Ihren Entwicklungscomputern festlegen können. Wenn Sie Umgebungsvariablen zum Speichern von Geheimnissen mit hierarchischen Namen verwenden, etwa die in den Konfigurationsabschnitten geschachtelten, müssen Sie die Variablen benennen, um die vollständige, mit Doppelpunkten (:) getrennte Hierarchie der Abschnitte einzubeziehen.

Zum Beispiel würde das Festlegen der Umgebungsvariablen `Logging:LogLevel:Default` auf `Debug` einem Konfigurationswert der folgenden JSON-Datei entsprechen:

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

Die Anwendung muss beim Erstellen eines IConfigurationRoot-Objekts nur „AddEnvironmentVariables“ in ihrer ConfigurationBuilder-Klasse aufrufen, um auf diese Werte von Umgebungsvariablen zuzugreifen.

Beachten Sie, dass Umgebungsvariablen in der Regel als Nur-Text gespeichert werden, wenn der Computer oder der Prozess mit den Umgebungsvariablen also gefährdet ist, sind die Werte der Umgebungsvariablen sichtbar.

## <a name="store-secrets-with-the-aspnet-core-secret-manager"></a>Speichern von Geheimnissen mit Secret Manager von ASP.NET Core

Das ASP.NET Core-Tool [Secret Manager](/aspnet/core/security/app-secrets#secret-manager) stellt eine weitere Methode bereit, um **während der Entwicklung** Geheimnisse aus dem Quellcode fernzuhalten. Um das Secret Manager-Tool verwenden zu können, installieren Sie das Paket **Microsoft.Extensions.Configuration.SecretManager** in Ihrer Projektdatei. Sobald diese Abhängigkeit vorhanden ist und wiederhergestellt wurde, kann der Befehl `dotnet user-secrets` verwendet werden, um den Wert der Geheimnisse über die Befehlszeile festzulegen. Diese Geheimnisse werden außerhalb vom Quellcode in einer JSON-Datei im Verzeichnis des Profils vom Benutzer (Details variieren je nach Betriebssystem) gespeichert.

Geheimnisse, die durch das Secret Manager-Tool festgelegt wurden, werden von der Eigenschaft `UserSecretsId` des Projekts organisiert, das die Geheimnisse verwendet. Aus diesem Grund sollten Sie sicherstellen, dass Sie die Eigenschaft UserSecretsId, wie im folgenden Codeausschnitt gezeigt wird, in Ihrer Projektdatei festlegen. Der Standardwert ist eine von Visual Studio zugewiesene GUID, aber die tatsächliche Zeichenfolge ist nicht wichtig, solange sie auf dem Computer eindeutig ist.

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

Sie können mit Secret Manager gespeicherte Geheimnisse in einer Anwendung verwenden, indem Sie `AddUserSecrets<T>` auf der Instanz ConfigurationBuilder aufrufen, um Geheimnisse für die Anwendung in der Konfiguration einzubeziehen. Der generische Parameter „T“ sollte ein Typ aus der Assembly sein, auf die „UserSecretId“ angewendet wurde. In der Regel ist die Verwendung von `AddUserSecrets<Startup>` in Ordnung.

`AddUserSecrets<Startup>()` wird bei Verwendung der Standardoptionen für die Entwicklungsumgebung einbezogen, wenn die `CreateDefaultBuilder`-Methode in *Program.cs* verwendet wird.

>[!div class="step-by-step"]
>[Zurück](authorization-net-microservices-web-applications.md)
>[Weiter](azure-key-vault-protects-secrets.md)
