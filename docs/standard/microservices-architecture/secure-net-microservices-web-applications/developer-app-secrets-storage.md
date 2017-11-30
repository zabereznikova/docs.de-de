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
# <a name="storing-application-secrets-safely-during-development"></a><span data-ttu-id="91092-104">Sicheres Speichern von Anwendung geheime Schlüssel während der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="91092-104">Storing application secrets safely during development</span></span>

<span data-ttu-id="91092-105">Um mit geschützten Ressourcen und anderen Diensten zu verbinden, müssen ASP.NET Core-Anwendungen in der Regel verwenden Sie Verbindungszeichenfolgen, Kennwörter oder andere Anmeldeinformationen, die vertraulichen Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="91092-105">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="91092-106">Diese vertrauliche Informationen werden bezeichnet *geheime Schlüssel*.</span><span class="sxs-lookup"><span data-stu-id="91092-106">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="91092-107">Es ist eine bewährte Methode, um geheime Schlüssel nicht im Quellcode einzuschließen und sicherlich nicht zum Speichern von geheimen Schlüsseln in der quellcodeverwaltung.</span><span class="sxs-lookup"><span data-stu-id="91092-107">It is a best practice to not include secrets in source code and certainly not to store secrets in source control.</span></span> <span data-ttu-id="91092-108">Stattdessen sollten Sie die ASP.NET Core Konfigurationsmodell verwenden, sicherer Speicherorte der geheime Schlüssel gelesen.</span><span class="sxs-lookup"><span data-stu-id="91092-108">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="91092-109">Trennen Sie die geheimen Schlüssel für den Zugriff auf die Entwicklung und staging-Ressourcen, von denen, die für den Zugriff auf Produktionsressourcen, verwendet wird, da verschiedene Personen Zugriff auf diese unterschiedliche Sätze von geheimen Schlüsseln benötigen.</span><span class="sxs-lookup"><span data-stu-id="91092-109">You should separate the secrets for accessing development and staging resources from those used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="91092-110">Zum Speichern von geheimen Schlüsseln, die während der Entwicklung verwendet, sind gebräuchlichen Verfahren entweder Speichern von geheimen Schlüsseln in Umgebungsvariablen oder mit dem ASP.NET Core geheimen Manager-Tool.</span><span class="sxs-lookup"><span data-stu-id="91092-110">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="91092-111">Bei der Speicher in produktionsumgebungen ist sicherer können Microservices geheime Schlüssel in einem Azure-Schlüsseltresor speichern.</span><span class="sxs-lookup"><span data-stu-id="91092-111">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="storing-secrets-in-environment-variables"></a><span data-ttu-id="91092-112">Das Speichern von geheimen Schlüsseln in Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="91092-112">Storing secrets in environment variables</span></span>

<span data-ttu-id="91092-113">Eine Möglichkeit, geheime Schlüssel außerhalb des Quellcodes zu halten ist für Entwickler festzulegende zeichenfolgenbasierte geheimen als [Umgebungsvariablen](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) auf ihren Entwicklungscomputern.</span><span class="sxs-lookup"><span data-stu-id="91092-113">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="91092-114">Bei Verwendung von Umgebungsvariablen zum Speichern von geheimen Schlüsseln mit hierarchischen Namen (die in den Konfigurationsabschnitten geschachtelt), erstellen Sie einen Namen für die Umgebungsvariablen, der die vollständige Hierarchie des geheimen Namen enthält, getrennt durch Doppelpunkte (:).</span><span class="sxs-lookup"><span data-stu-id="91092-114">When you use environment variables to store secrets with hierarchical names (those nested in configuration sections), create a name for the environment variables that includes the full hierarchy of the secret’s name, delimited with colons (:).</span></span>

<span data-ttu-id="91092-115">Beispielsweise würde eine Umgebungsvariable Protokollierung: LogLevel:Default Debuggen festlegen entsprechen, einen Konfigurationswert aus den folgenden JSON-Datei folgendermaßen lauten:</span><span class="sxs-lookup"><span data-stu-id="91092-115">For example, setting an environment variable Logging:LogLevel:Default to Debug would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="91092-116">Zugreifen auf diese Werte von Umgebungsvariablen, benötigt die Anwendung nur AddEnvironmentVariables seine ConfigurationBuilder aufgerufen, wenn ein IConfigurationRoot-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="91092-116">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="91092-117">Beachten Sie, dass die Umgebungsvariablen in der Regel als nur-Text gespeichert werden, wenn der Computer oder der Prozess mit der Umgebungsvariablen gefährdet ist, die Werte für Umgebungsvariablen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="91092-117">Note that environment variables are generally stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a><span data-ttu-id="91092-118">Das Speichern von geheimen Schlüsseln, die mit dem ASP.NET Core Secret-Manager</span><span class="sxs-lookup"><span data-stu-id="91092-118">Storing secrets using the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="91092-119">Die ASP.NET Core [geheimen Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) Tool bietet eine andere Methode halten geheimen Schlüssel aus dem Quellcode.</span><span class="sxs-lookup"><span data-stu-id="91092-119">The ASP.NET Core [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code.</span></span> <span data-ttu-id="91092-120">Um den geheimen Schlüssel-Manager-Tool verwenden zu können, schließen Sie eine toolreferenz (DotNetCliToolReference) des Microsoft.Extensions.SecretManager.Tools-Pakets in der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="91092-120">To use the Secret Manager tool, include a tools reference (DotNetCliToolReference) to the Microsoft.Extensions.SecretManager.Tools package in your project file.</span></span> <span data-ttu-id="91092-121">Sobald diese Abhängigkeit vorhanden ist und wiederhergestellt wurde, kann die Dotnet vertrauliche Benutzerdaten-Befehl verwendet werden, um den Wert der geheimen Schlüssel über die Befehlszeile festzulegen.</span><span class="sxs-lookup"><span data-stu-id="91092-121">Once that dependency is present and has been restored, the dotnet user-secrets command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="91092-122">Diese geheimen Informationen werden in einer JSON-Datei im Verzeichnis des Benutzers Profil (Details variieren von OS), von Quellcode gespeichert.</span><span class="sxs-lookup"><span data-stu-id="91092-122">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="91092-123">Geheime Schlüssel festlegen, indem das Tool Secret-Manager werden von der UserSecretsId-Eigenschaft des Projekts organisiert, die die geheimen Schlüssel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="91092-123">Secrets set by the Secret Manager tool are organized by the UserSecretsId property of the project that is using the secrets.</span></span> <span data-ttu-id="91092-124">Aus diesem Grund müssen Sie Sie sicher, dass die UserSecretsId-Eigenschaft in der Projektdatei (wie im folgenden Codeausschnitt gezeigt) festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="91092-124">Therefore, you must be sure to set the UserSecretsId property in your project file (as shown in the snippet below).</span></span> <span data-ttu-id="91092-125">Die tatsächliche Zeichenfolge, die verwendet werden, weil die ID ist nicht wichtig, solange er eindeutig im Projekt ist.</span><span class="sxs-lookup"><span data-stu-id="91092-125">The actual string used as the ID is not important as long as it is unique in the project.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="91092-126">Mit geheimen Schlüsseln mit geheimen Manager in einer Anwendung gespeichert erfolgt durch Aufrufen von AddUserSecrets&lt;T&gt; für die Instanz ConfigurationBuilder geheime Schlüssel für die Anwendung in der Konfiguration enthalten.</span><span class="sxs-lookup"><span data-stu-id="91092-126">Using secrets stored with Secret Manager in an application is accomplished by calling AddUserSecrets&lt;T&gt; on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="91092-127">Der generische Parameter T muss einen Typ aus der Assembly, die auf die UserSecretId angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="91092-127">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="91092-128">In der Regel mit AddUserSecrets&lt;Start&gt; ist in Ordnung.</span><span class="sxs-lookup"><span data-stu-id="91092-128">Usually using AddUserSecrets&lt;Startup&gt; is fine.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="91092-129">[Vorherigen] (Autorisierung-Net-Microservices-Web-applications.md) [weiter] (Azure-Schlüssel-Tresor-schützt-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="91092-129">[Previous] (authorization-net-microservices-web-applications.md) [Next] (azure-key-vault-protects-secrets.md)</span></span>
