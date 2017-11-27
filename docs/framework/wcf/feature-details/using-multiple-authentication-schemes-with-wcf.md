---
title: Verwenden von mehreren Authentifizierungsschemen mit WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: db2545470c416fe066226124fb7833ef5d9e5d13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a><span data-ttu-id="0b8ed-102">Verwenden von mehreren Authentifizierungsschemen mit WCF</span><span class="sxs-lookup"><span data-stu-id="0b8ed-102">Using Multiple Authentication Schemes with WCF</span></span>
<span data-ttu-id="0b8ed-103">Mit WCF können Sie nun mehrere Authentifizierungsschemas für einen einzelnen Endpunkt angeben.</span><span class="sxs-lookup"><span data-stu-id="0b8ed-103">WCF now allows you to specify multiple authentication schemes on a single endpoint.</span></span> <span data-ttu-id="0b8ed-104">Darüber hinaus können webgehostete Dienste ihre Authentifizierungseinstellungen direkt von IIS erben.</span><span class="sxs-lookup"><span data-stu-id="0b8ed-104">Furthermore web hosted services can inherit their authentication settings directly from IIS.</span></span> <span data-ttu-id="0b8ed-105">Selbst gehostete Dienste können angeben, welche Authentifizierungsschemas verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0b8ed-105">Self-hosted services can specify what authentication schemes can be used.</span></span> <span data-ttu-id="0b8ed-106">Weitere Informationen zum Einrichten der Authentifizierungseinstellungen in IIS finden Sie unter [IIS-Authentifizierung](http://go.microsoft.com/fwlink/?LinkId=232458)</span><span class="sxs-lookup"><span data-stu-id="0b8ed-106">For more information about setting authentication settings in IIS, see [IIS Authentication](http://go.microsoft.com/fwlink/?LinkId=232458)</span></span>  
  
## <a name="iis-hosted-services"></a><span data-ttu-id="0b8ed-107">IIS-gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="0b8ed-107">IIS-Hosted Services</span></span>  
 <span data-ttu-id="0b8ed-108">Legen Sie für IIS-gehostete Dienste die Authentifizierungsschemas fest, die Sie in IIS verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0b8ed-108">For IIS-hosted services, set the authentication schemes you wish to use in IIS.</span></span> <span data-ttu-id="0b8ed-109">Geben Sie dann in der Datei "Web.config" des Diensts, in der Bindungskonfiguration ClientCredential-Typ als "InheritedFromHost" wie im folgenden XML-Ausschnitt gezeigt:</span><span class="sxs-lookup"><span data-stu-id="0b8ed-109">Then in your service’s web.config file, in your binding configuration specify clientCredential type as "InheritedFromHost" as shown in the following XML snippet:</span></span>  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 <span data-ttu-id="0b8ed-110">Sie können angeben, dass nur eine Teilmenge der Authentifizierungsschemas mit Ihrem Dienst mithilfe von "serviceauthenticationbehavior" verwendet werden soll oder die \<ServiceAuthenticationManager >-Element.</span><span class="sxs-lookup"><span data-stu-id="0b8ed-110">You can specify that you only want a subset of authentication schemes to be used with your service using the ServiceAuthenticationBehavior or the \<serviceAuthenticationManager> element.</span></span> <span data-ttu-id="0b8ed-111">Beim Konfigurieren im Code verwenden Sie ServiceAuthenticationBehavior wie im folgenden Codeausschnitt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0b8ed-111">When configuring this in code use the ServiceAuthenticationBehavior as shown in the following code snippet.</span></span>  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 <span data-ttu-id="0b8ed-112">Wenn Sie dies in einer Konfigurationsdatei konfigurieren, verwenden die \<ServiceAuthenticationManager >-Element wie im folgenden XML-Ausschnitt gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b8ed-112">When configuring this in a config file, use the \<serviceAuthenticationManager> element as shown in the following XML snippet.</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="0b8ed-113">Dadurch wird sichergestellt, dass nur eine Teilmenge der hier aufgeführten Authentifizierungsschemas für den Dienstendpunkt infrage kommt, je nachdem, was in IIS ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="0b8ed-113">This will ensure that only a subset of the authentication schemes listed here will be considered for applying on the service endpoint, depending on what is selected in the IIS.</span></span> <span data-ttu-id="0b8ed-114">Dies bedeutet, dass ein Entwickler z. B. die Standardauthentifizierung aus der Liste ausschließen kann, indem er sie in der serviceAuthenticationManager-Liste auslässt. Sie wird auch nicht auf den Dienstendpunkt angewendet, wenn sie in IIS aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0b8ed-114">This means that a developer can exclude say Basic auth from the list by omitting it from the serviceAuthenticationManager listing and even if it is enabled in IIS, it will not be applied on the service endpoint</span></span>  
  
## <a name="self-hosted-services"></a><span data-ttu-id="0b8ed-115">Selbst gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="0b8ed-115">Self-Hosted Services</span></span>  
 <span data-ttu-id="0b8ed-116">Selbst gehostete Dienste werden geringfügig anders konfiguriert, da keine Einstellungen von IIS geerbt werden können.</span><span class="sxs-lookup"><span data-stu-id="0b8ed-116">Self-hosted services are configured a bit differently since there is no IIS to inherit settings from.</span></span> <span data-ttu-id="0b8ed-117">Hier verwenden Sie die \<ServiceAuthenticationManager >-Element oder "serviceauthenticationbehavior", um die Authentifizierungseinstellungen anzugeben, die vererbt werden.</span><span class="sxs-lookup"><span data-stu-id="0b8ed-117">Here you use the \<serviceAuthenticationManager> element or ServiceAuthenticationBehavior to specify the authentication settings that will be inherited.</span></span> <span data-ttu-id="0b8ed-118">Der Code sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="0b8ed-118">In code it looks like this:</span></span>  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 <span data-ttu-id="0b8ed-119">In der config-Datei sieht das wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="0b8ed-119">In config, it looks like this:</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 <span data-ttu-id="0b8ed-120">Außerdem können Sie InheritFromHost in den Bindungseinstellungen angeben, wie im folgenden XML-Ausschnitt gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b8ed-120">And then you can specify InheritFromHost in your binding settings as shown in the following XML snippet.</span></span>  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 <span data-ttu-id="0b8ed-121">Alternativ können Sie die Authentifizierungsschemas in einer benutzerdefinierten Bindung angeben, indem Sie die Authentifizierungsschemas für das HTTP-Transportbindungselement festlegen, wie im folgenden Konfigurationsausschnitt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0b8ed-121">Alternatively, you can specify the authentication schemes in a custom binding, by setting the authentication schemes on the HTTP transport binding element, as shown in the following config snippet.</span></span>  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b8ed-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b8ed-122">See Also</span></span>  
 [<span data-ttu-id="0b8ed-123">Bindungen und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0b8ed-123">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [<span data-ttu-id="0b8ed-124">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="0b8ed-124">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [<span data-ttu-id="0b8ed-125">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="0b8ed-125">Configuring System-Provided Bindings</span></span>](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="0b8ed-126">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="0b8ed-126">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="0b8ed-127">Bindungen</span><span class="sxs-lookup"><span data-stu-id="0b8ed-127">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [<span data-ttu-id="0b8ed-128">Bindungen</span><span class="sxs-lookup"><span data-stu-id="0b8ed-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [<span data-ttu-id="0b8ed-129">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="0b8ed-129">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)
