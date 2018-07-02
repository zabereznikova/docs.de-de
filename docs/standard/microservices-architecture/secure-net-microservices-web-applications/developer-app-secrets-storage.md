---
title: Sicheres Speichern von Anwendungsgeheimnissen während der Entwicklung
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Sicheres Speichern von Anwendungsgeheimnissen während der Entwicklung
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 560120db35ae190bdef1f95d72ac1e5de697124e
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105945"
---
# <a name="storing-application-secrets-safely-during-development"></a><span data-ttu-id="c0c33-103">Sicheres Speichern von Anwendungsgeheimnissen während der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="c0c33-103">Storing application secrets safely during development</span></span>

<span data-ttu-id="c0c33-104">Zum Verbinden mit geschützten Ressourcen und anderen Diensten benötigen ASP.NET Core-Anwendungen in der Regel Verbindungszeichenfolgen, Kennwörter oder andere Anmeldeinformationen, die vertrauliche Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c0c33-104">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="c0c33-105">Diese vertraulichen Informationen werden *Geheimnisse* genannt.</span><span class="sxs-lookup"><span data-stu-id="c0c33-105">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="c0c33-106">Es stellt eine bewährte Methode dar, Geheimnisse nicht in den Quellcode einzufügen und nicht in der Quellcodeverwaltung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c0c33-106">It is a best practice to not include secrets in source code and certainly not to store secrets in source control.</span></span> <span data-ttu-id="c0c33-107">Stattdessen sollten Sie das Konfigurationsmodell von ASP.NET Core verwenden, um Geheimnisse aus sichereren Speicherorten zu lesen.</span><span class="sxs-lookup"><span data-stu-id="c0c33-107">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="c0c33-108">Sie sollten die Geheimnisse für den Zugriff auf Entwicklungs- und Stagingressourcen von denen trennen, die für den Zugriff auf Produktionsressourcen verwendet werden, da verschiedene Personen Zugriff auf diese verschiedenen Geheimnisse benötigen.</span><span class="sxs-lookup"><span data-stu-id="c0c33-108">You should separate the secrets for accessing development and staging resources from those used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="c0c33-109">Beim Speichern von Geheimnissen, die während der Entwicklung genutzt werden, ist es gebräuchlich, diese entweder in Umgebungsvariablen oder mithilfe des Secret Manager-Tools von ASP.NET Core zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c0c33-109">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="c0c33-110">Für eine sicherere Speicherung in Produktionsumgebungen können Microservices Geheimnisse in Azure Key Vault speichern.</span><span class="sxs-lookup"><span data-stu-id="c0c33-110">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="storing-secrets-in-environment-variables"></a><span data-ttu-id="c0c33-111">Speichern von Geheimnissen in Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="c0c33-111">Storing secrets in environment variables</span></span>

<span data-ttu-id="c0c33-112">Eine Möglichkeit, um Geheimnisse aus dem Quellcode fernzuhalten, besteht darin, dass Entwickler zeichenfolgenbasierte Geheimnisse als [Umgebungsvariablen](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) auf Ihren Entwicklungscomputern festlegen können.</span><span class="sxs-lookup"><span data-stu-id="c0c33-112">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="c0c33-113">Wenn Sie Umgebungsvariablen zum Speichern von Geheimnissen mit hierarchischen Namen verwenden (die in den Konfigurationsabschnitten geschachtelt sind), erstellen Sie einen Namen für die Umgebungsvariablen, der eine vollständige, mit Doppelpunkten (:) getrennte Hierarchie des Namen des Geheimnisses enthält.</span><span class="sxs-lookup"><span data-stu-id="c0c33-113">When you use environment variables to store secrets with hierarchical names (those nested in configuration sections), create a name for the environment variables that includes the full hierarchy of the secret’s name, delimited with colons (:).</span></span>

<span data-ttu-id="c0c33-114">Zum Beispiel würde das Festlegen der Umgebungsvariable „Logging:LogLevel:Default“ auf „Debug“ einem Konfigurationswert der folgenden JSON-Datei entsprechen:</span><span class="sxs-lookup"><span data-stu-id="c0c33-114">For example, setting an environment variable Logging:LogLevel:Default to Debug would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="c0c33-115">Die Anwendung muss beim Erstellen eines IConfigurationRoot-Objekts nur „AddEnvironmentVariables“ in ihrer ConfigurationBuilder-Klasse aufrufen, um auf diese Werte von Umgebungsvariablen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c0c33-115">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="c0c33-116">Beachten Sie, dass Umgebungsvariablen in der Regel als Nur-Text gespeichert werden, wenn der Computer oder der Prozess mit den Umgebungsvariablen also gefährdet ist, sind die Werte der Umgebungsvariable sichtbar.</span><span class="sxs-lookup"><span data-stu-id="c0c33-116">Note that environment variables are generally stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a><span data-ttu-id="c0c33-117">Speichern von Geheimnissen mit Secret Manager von ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c0c33-117">Storing secrets using the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="c0c33-118">Das ASP.NET Core-Tool [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) stellt eine weitere Methode bereit, um Geheimnisse aus dem Quellcode fernzuhalten.</span><span class="sxs-lookup"><span data-stu-id="c0c33-118">The ASP.NET Core [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code.</span></span> <span data-ttu-id="c0c33-119">Fügen Sie eine Referenz zu Tools (DotNetCliToolReference) in das Paket „Microsoft.Extensions.SecretManager.Tools“ in Ihrer Projektdatei ein, um das Secret Manager-Tool zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0c33-119">To use the Secret Manager tool, include a tools reference (DotNetCliToolReference) to the Microsoft.Extensions.SecretManager.Tools package in your project file.</span></span> <span data-ttu-id="c0c33-120">Sobald diese Abhängigkeit vorhanden ist und wiederhergestellt wurde, kann der Befehl „dotnet user-secrets“ verwendet werden, um den Wert der Geheimnisse über die Befehlszeile festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c0c33-120">Once that dependency is present and has been restored, the dotnet user-secrets command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="c0c33-121">Diese Geheimnisse werden außerhalb vom Quellcode in einer JSON-Datei im Verzeichnis des Profils vom Benutzer (Details variieren je nach Betriebssystem) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c0c33-121">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="c0c33-122">Geheimnisse, die durch das Secret Manager-Tool festgelegt wurden, werden von der Eigenschaft „UserSecretsId“ des Projekts organisiert, das die Geheimnisse verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0c33-122">Secrets set by the Secret Manager tool are organized by the UserSecretsId property of the project that is using the secrets.</span></span> <span data-ttu-id="c0c33-123">Aus diesem Grund sollten Sie sicherstellen, dass Sie die Eigenschaft „UserSecretsId“ (wie im folgenden Codeausschnitt gezeigt wird) in Ihrer Projektdatei festlegen.</span><span class="sxs-lookup"><span data-stu-id="c0c33-123">Therefore, you must be sure to set the UserSecretsId property in your project file (as shown in the snippet below).</span></span> <span data-ttu-id="c0c33-124">Die tatsächliche Zeichenfolge, die als ID verwendet wird, ist nicht wichtig, so lange sie im Projekt eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="c0c33-124">The actual string used as the ID is not important as long as it is unique in the project.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="c0c33-125">Sie können mit Secret Manager gespeicherte Geheimnisse in einer Anwendung verwenden, indem Sie „AddUserSecrets&lt;T&gt;“ auf der Instanz „ConfigurationBuilder“ aufrufen, um Geheimnisse für die Anwendung in der Konfiguration zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="c0c33-125">Using secrets stored with Secret Manager in an application is accomplished by calling AddUserSecrets&lt;T&gt; on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="c0c33-126">Der generische Parameter „T“ sollte ein Typ aus der Assembly sein, auf die „UserSecretId“ angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c0c33-126">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="c0c33-127">In der Regel ist das Verwenden von „AddUserSecrets&lt;Startup&gt;“ in Ordnung.</span><span class="sxs-lookup"><span data-stu-id="c0c33-127">Usually using AddUserSecrets&lt;Startup&gt; is fine.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="c0c33-128">[Zurück](authorization-net-microservices-web-applications.md)
[Weiter](azure-key-vault-protects-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="c0c33-128">[Previous](authorization-net-microservices-web-applications.md)
[Next](azure-key-vault-protects-secrets.md)</span></span>
