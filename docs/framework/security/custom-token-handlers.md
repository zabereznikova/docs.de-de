---
title: Benutzerdefinierte Tokenhandler
ms.date: 03/30/2017
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
author: BrucePerlerMS
ms.openlocfilehash: f7d611bf396f028ff23a39cd529825f99fec300a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650434"
---
# <a name="custom-token-handlers"></a><span data-ttu-id="2d00a-102">Benutzerdefinierte Tokenhandler</span><span class="sxs-lookup"><span data-stu-id="2d00a-102">Custom Token Handlers</span></span>
<span data-ttu-id="2d00a-103">In diesem Thema werden Tokenhandler in WIF und ihre Verwendung zur Verarbeitung von Token erläutert.</span><span class="sxs-lookup"><span data-stu-id="2d00a-103">This topic discusses token handlers in WIF and how they are used to process tokens.</span></span> <span data-ttu-id="2d00a-104">Das Thema behandelt auch die Vorgehensweise zum Erstellen von benutzerdefinierten Tokenhandlern für Tokentypen, die nicht standardmäßig in WIF unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2d00a-104">The topic also covers what is necessary to create custom token handlers for token types that are not supported by default in WIF.</span></span>  
  
## <a name="introduction-to-token-handlers-in-wif"></a><span data-ttu-id="2d00a-105">Einführung in Tokenhandler in WIF</span><span class="sxs-lookup"><span data-stu-id="2d00a-105">Introduction to Token Handlers in WIF</span></span>  
 <span data-ttu-id="2d00a-106">WIF verwendet Sicherheitstokenhandler zum Erstellen, Lesen, Schreiben und Überprüfen von Token für eine Anwendung der vertrauenden Seite (Relying Party, RP) oder einen Sicherheitstokendienst (Security Token Service, STS).</span><span class="sxs-lookup"><span data-stu-id="2d00a-106">WIF relies on security token handlers to create, read, write, and validate tokens for a relying party (RP) application or a security token service (STS).</span></span> <span data-ttu-id="2d00a-107">Tokenhandler sind Erweiterungspunkte, um der WIF-Pipeline einen benutzerdefinierten Tokenhandler hinzuzufügen oder die Tokenverwaltung eines vorhandenen Tokenhandlers anzupassen.</span><span class="sxs-lookup"><span data-stu-id="2d00a-107">Token handlers are extensibility points for you to add a custom token handler in the WIF pipeline, or to customize the way that an existing token handler manages tokens.</span></span> <span data-ttu-id="2d00a-108">WIF stellt neun integrierte Sicherheitstokenhandler bereit, deren Funktionen nach Bedarf geändert oder vollständig überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="2d00a-108">WIF provides nine built-in security token handlers that can be modified or entirely overridden to change the functionality as necessary.</span></span>  
  
## <a name="built-in-security-token-handlers-in-wif"></a><span data-ttu-id="2d00a-109">Integrierte Sicherheitstokenhandler in WIF</span><span class="sxs-lookup"><span data-stu-id="2d00a-109">Built-In Security Token Handlers in WIF</span></span>  
 <span data-ttu-id="2d00a-110">WIF 4.5 beinhaltet neun Klassen für Sicherheitstokenhandler, die von der abstrakten Basisklasse <xref:System.IdentityModel.Tokens.SecurityTokenHandler> abgeleitet werden:</span><span class="sxs-lookup"><span data-stu-id="2d00a-110">WIF 4.5 includes nine security token handler classes that derive from the abstract base class <xref:System.IdentityModel.Tokens.SecurityTokenHandler>:</span></span>  
  
- <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## <a name="adding-a-custom-token-handler"></a><span data-ttu-id="2d00a-111">Hinzufügen eines benutzerdefinierten Tokenhandlers</span><span class="sxs-lookup"><span data-stu-id="2d00a-111">Adding a Custom Token Handler</span></span>  
 <span data-ttu-id="2d00a-112">Einige Tokentypen, wie z.B. einfache Webtoken (Simple Web Tokens, SWT) und JSON-Webtoken (JWT), verfügen über keine integrierten WIF-Sicherheitstokenhandler.</span><span class="sxs-lookup"><span data-stu-id="2d00a-112">Some token types, such as Simple Web Tokens (SWT) and JSON Web Tokens (JWT) do not have built-in token handlers provided by WIF.</span></span> <span data-ttu-id="2d00a-113">Bei diesen Tokentypen und bei Typen, die nicht über einen integrierten Handler verfügen, müssen Sie folgendermaßen vorgehen, um einen benutzerdefinierten Tokenhandler zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d00a-113">For these token types and for others that do not have a built-in handler, you need to perform the following steps to create a custom token handler.</span></span>  
  
#### <a name="adding-a-custom-token-handler"></a><span data-ttu-id="2d00a-114">Hinzufügen eines benutzerdefinierten Tokenhandlers</span><span class="sxs-lookup"><span data-stu-id="2d00a-114">Adding a custom token handler</span></span>  
  
1. <span data-ttu-id="2d00a-115">Erstellen Sie eine neue Klasse, die von <xref:System.IdentityModel.Tokens.SecurityTokenHandler> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="2d00a-115">Create a new class that derives from <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.</span></span>  
  
2. <span data-ttu-id="2d00a-116">Überschreiben Sie die folgenden Methoden, und stellen Sie Ihre eigene Implementierung bereit:</span><span class="sxs-lookup"><span data-stu-id="2d00a-116">Override the following methods and provide your own implementation:</span></span>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3. <span data-ttu-id="2d00a-117">Fügen Sie im **\<system.identityModel>**-Abschnitt für WIF in der Datei *Web.config* oder der Datei *App.config* dem neuen benutzerdefinierten Tokenhandler einen Verweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="2d00a-117">Add a reference to the new custom token handler in the *Web.config* or *App.config* file, within the **\<system.identityModel>** section that applies to WIF.</span></span> <span data-ttu-id="2d00a-118">Das folgende Konfigurationsmarkup gibt z.B. einen neuen Tokenhandler mit dem Namen **MyCustomTokenHandler** an, der sich im Namespace **CustomToken** befindet.</span><span class="sxs-lookup"><span data-stu-id="2d00a-118">For example, the following configuration markup specifies a new token handler named **MyCustomTokenHandler** that resides in the **CustomToken** namespace.</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     <span data-ttu-id="2d00a-119">Beachten Sie, dass Sie beim Bereitstellen Ihres eigenen Tokenhandlers zur Behandlung eines Tokentyps mit integriertem Tokenhandler ein **\<remove>**-Element hinzufügen müssen, um den Standardhandler zu löschen und dafür den benutzerdefinierten Handler zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d00a-119">Note that if you are providing your own token handler to handle a token type that already has a built-in token handler, you need to add a **\<remove>** element to drop the default handler and use your custom handler instead.</span></span> <span data-ttu-id="2d00a-120">Die folgende Konfiguration ersetzt beispielsweise den standardmäßigen <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> durch den benutzerdefinierten Tokenhandler:</span><span class="sxs-lookup"><span data-stu-id="2d00a-120">For example, the following configuration replaces the default <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> with the custom token handler:</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <remove type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcdefg123456789">  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```
