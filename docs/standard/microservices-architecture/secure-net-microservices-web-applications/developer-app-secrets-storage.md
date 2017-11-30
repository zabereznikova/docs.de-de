---
title: "Sicheres Speichern von Anwendung geheime Schlüssel während der Entwicklung"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Sicheres Speichern von Anwendung geheime Schlüssel während der Entwicklung"
keywords: Docker, Microservices, ASP.NET, Container
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f1b8b257a3e677c7e665e1d394a8adf7e651bec2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="storing-application-secrets-safely-during-development"></a>Sicheres Speichern von Anwendung geheime Schlüssel während der Entwicklung

Um mit geschützten Ressourcen und anderen Diensten zu verbinden, müssen ASP.NET Core-Anwendungen in der Regel verwenden Sie Verbindungszeichenfolgen, Kennwörter oder andere Anmeldeinformationen, die vertraulichen Informationen enthalten. Diese vertrauliche Informationen werden bezeichnet *geheime Schlüssel*. Es ist eine bewährte Methode, um geheime Schlüssel nicht im Quellcode einzuschließen und sicherlich nicht zum Speichern von geheimen Schlüsseln in der quellcodeverwaltung. Stattdessen sollten Sie die ASP.NET Core Konfigurationsmodell verwenden, sicherer Speicherorte der geheime Schlüssel gelesen.

Trennen Sie die geheimen Schlüssel für den Zugriff auf die Entwicklung und staging-Ressourcen, von denen, die für den Zugriff auf Produktionsressourcen, verwendet wird, da verschiedene Personen Zugriff auf diese unterschiedliche Sätze von geheimen Schlüsseln benötigen. Zum Speichern von geheimen Schlüsseln, die während der Entwicklung verwendet, sind gebräuchlichen Verfahren entweder Speichern von geheimen Schlüsseln in Umgebungsvariablen oder mit dem ASP.NET Core geheimen Manager-Tool. Bei der Speicher in produktionsumgebungen ist sicherer können Microservices geheime Schlüssel in einem Azure-Schlüsseltresor speichern.

## <a name="storing-secrets-in-environment-variables"></a>Das Speichern von geheimen Schlüsseln in Umgebungsvariablen

Eine Möglichkeit, geheime Schlüssel außerhalb des Quellcodes zu halten ist für Entwickler festzulegende zeichenfolgenbasierte geheimen als [Umgebungsvariablen](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) auf ihren Entwicklungscomputern. Bei Verwendung von Umgebungsvariablen zum Speichern von geheimen Schlüsseln mit hierarchischen Namen (die in den Konfigurationsabschnitten geschachtelt), erstellen Sie einen Namen für die Umgebungsvariablen, der die vollständige Hierarchie des geheimen Namen enthält, getrennt durch Doppelpunkte (:).

Beispielsweise würde eine Umgebungsvariable Protokollierung: LogLevel:Default Debuggen festlegen entsprechen, einen Konfigurationswert aus den folgenden JSON-Datei folgendermaßen lauten:

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

Zugreifen auf diese Werte von Umgebungsvariablen, benötigt die Anwendung nur AddEnvironmentVariables seine ConfigurationBuilder aufgerufen, wenn ein IConfigurationRoot-Objekt zu erstellen.

Beachten Sie, dass die Umgebungsvariablen in der Regel als nur-Text gespeichert werden, wenn der Computer oder der Prozess mit der Umgebungsvariablen gefährdet ist, die Werte für Umgebungsvariablen angezeigt werden.

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a>Das Speichern von geheimen Schlüsseln, die mit dem ASP.NET Core Secret-Manager

Die ASP.NET Core [geheimen Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) Tool bietet eine andere Methode halten geheimen Schlüssel aus dem Quellcode. Um den geheimen Schlüssel-Manager-Tool verwenden zu können, schließen Sie eine toolreferenz (DotNetCliToolReference) des Microsoft.Extensions.SecretManager.Tools-Pakets in der Projektdatei. Sobald diese Abhängigkeit vorhanden ist und wiederhergestellt wurde, kann die Dotnet vertrauliche Benutzerdaten-Befehl verwendet werden, um den Wert der geheimen Schlüssel über die Befehlszeile festzulegen. Diese geheimen Informationen werden in einer JSON-Datei im Verzeichnis des Benutzers Profil (Details variieren von OS), von Quellcode gespeichert.

Geheime Schlüssel festlegen, indem das Tool Secret-Manager werden von der UserSecretsId-Eigenschaft des Projekts organisiert, die die geheimen Schlüssel verwendet wird. Aus diesem Grund müssen Sie Sie sicher, dass die UserSecretsId-Eigenschaft in der Projektdatei (wie im folgenden Codeausschnitt gezeigt) festgelegt sein. Die tatsächliche Zeichenfolge, die verwendet werden, weil die ID ist nicht wichtig, solange er eindeutig im Projekt ist.

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

Mit geheimen Schlüsseln mit geheimen Manager in einer Anwendung gespeichert erfolgt durch Aufrufen von AddUserSecrets&lt;T&gt; für die Instanz ConfigurationBuilder geheime Schlüssel für die Anwendung in der Konfiguration enthalten. Der generische Parameter T muss einen Typ aus der Assembly, die auf die UserSecretId angewendet wurde. In der Regel mit AddUserSecrets&lt;Start&gt; ist in Ordnung.


>[!div class="step-by-step"]
[Vorherigen] (Autorisierung-Net-Microservices-Web-applications.md) [weiter] (Azure-Schlüssel-Tresor-schützt-secrets.md)
