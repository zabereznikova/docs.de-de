---
title: Sicheres Speichern von Anwendungsgeheimnissen während der Entwicklung
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Sicheres Speichern von Anwendungsgeheimnissen während der Entwicklung
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 6f5dfbb53b99fec4d7cc66c528fe866c71c2172f
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143869"
---
# <a name="storing-application-secrets-safely-during-development"></a>Sicheres Speichern von Anwendungsgeheimnissen während der Entwicklung

Zum Verbinden mit geschützten Ressourcen und anderen Diensten benötigen ASP.NET Core-Anwendungen in der Regel Verbindungszeichenfolgen, Kennwörter oder andere Anmeldeinformationen, die vertrauliche Informationen enthalten. Diese vertraulichen Informationen werden *Geheimnisse* genannt. Es stellt eine bewährte Methode dar, Geheimnisse nicht in den Quellcode einzufügen und nicht in der Quellcodeverwaltung zu speichern. Stattdessen sollten Sie das Konfigurationsmodell von ASP.NET Core verwenden, um Geheimnisse aus sichereren Speicherorten zu lesen.

Sie sollten die Geheimnisse für den Zugriff auf Entwicklungs- und Stagingressourcen von denen trennen, die für den Zugriff auf Produktionsressourcen verwendet werden, da verschiedene Personen Zugriff auf diese verschiedenen Geheimnisse benötigen. Beim Speichern von Geheimnissen, die während der Entwicklung genutzt werden, ist es gebräuchlich, diese entweder in Umgebungsvariablen oder mithilfe des Secret Manager-Tools von ASP.NET Core zu speichern. Für eine sicherere Speicherung in Produktionsumgebungen können Microservices Geheimnisse in Azure Key Vault speichern.

## <a name="storing-secrets-in-environment-variables"></a>Speichern von Geheimnissen in Umgebungsvariablen

Eine Möglichkeit, um Geheimnisse aus dem Quellcode fernzuhalten, besteht darin, dass Entwickler zeichenfolgenbasierte Geheimnisse als [Umgebungsvariablen](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) auf Ihren Entwicklungscomputern festlegen können. Wenn Sie Umgebungsvariablen zum Speichern von Geheimnissen mit hierarchischen Namen verwenden (die in den Konfigurationsabschnitten geschachtelt sind), erstellen Sie einen Namen für die Umgebungsvariablen, der eine vollständige, mit Doppelpunkten (:) getrennte Hierarchie des Namen des Geheimnisses enthält.

Zum Beispiel würde das Festlegen der Umgebungsvariable „Logging:LogLevel:Default“ auf „Debug“ einem Konfigurationswert der folgenden JSON-Datei entsprechen:

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

Beachten Sie, dass Umgebungsvariablen in der Regel als Nur-Text gespeichert werden, wenn der Computer oder der Prozess mit den Umgebungsvariablen also gefährdet ist, sind die Werte der Umgebungsvariable sichtbar.

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a>Speichern von Geheimnissen mit Secret Manager von ASP.NET Core

Das ASP.NET Core-Tool [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) stellt eine weitere Methode bereit, um Geheimnisse aus dem Quellcode fernzuhalten. Fügen Sie eine Referenz zu Tools (DotNetCliToolReference) in das Paket „Microsoft.Extensions.SecretManager.Tools“ in Ihrer Projektdatei ein, um das Secret Manager-Tool zu verwenden. Sobald diese Abhängigkeit vorhanden ist und wiederhergestellt wurde, kann der Befehl „dotnet user-secrets“ verwendet werden, um den Wert der Geheimnisse über die Befehlszeile festzulegen. Diese Geheimnisse werden außerhalb vom Quellcode in einer JSON-Datei im Verzeichnis des Profils vom Benutzer (Details variieren je nach Betriebssystem) gespeichert.

Geheimnisse, die durch das Secret Manager-Tool festgelegt wurden, werden von der Eigenschaft „UserSecretsId“ des Projekts organisiert, das die Geheimnisse verwendet. Aus diesem Grund sollten Sie sicherstellen, dass Sie die Eigenschaft „UserSecretsId“ (wie im folgenden Codeausschnitt gezeigt wird) in Ihrer Projektdatei festlegen. Die tatsächliche Zeichenfolge, die als ID verwendet wird, ist nicht wichtig, so lange sie im Projekt eindeutig ist.

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

Sie können mit Secret Manager gespeicherte Geheimnisse in einer Anwendung verwenden, indem Sie „AddUserSecrets&lt;T&gt;“ auf der Instanz „ConfigurationBuilder“ aufrufen, um Geheimnisse für die Anwendung in der Konfiguration zu enthalten. Der generische Parameter „T“ sollte ein Typ aus der Assembly sein, auf die „UserSecretId“ angewendet wurde. In der Regel ist das Verwenden von „AddUserSecrets&lt;Startup&gt;“ in Ordnung.


>[!div class="step-by-step"]
>[Zurück](authorization-net-microservices-web-applications.md)
>[Weiter](azure-key-vault-protects-secrets.md)