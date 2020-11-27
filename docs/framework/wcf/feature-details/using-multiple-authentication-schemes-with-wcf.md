---
title: Verwenden von mehreren Authentifizierungsschemen mit WCF
ms.date: 03/30/2017
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
ms.openlocfilehash: 3aae9bff4300af97f7b179d9d8115340a26e715a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289424"
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a>Verwenden von mehreren Authentifizierungsschemen mit WCF

Mit WCF können Sie nun mehrere Authentifizierungsschemas für einen einzelnen Endpunkt angeben. Darüber hinaus können webgehostete Dienste ihre Authentifizierungseinstellungen direkt von IIS erben. Selbst gehostete Dienste können angeben, welche Authentifizierungsschemas verwendet werden können. Weitere Informationen zum Festlegen von Authentifizierungs Einstellungen in IIS finden Sie unter [IIS-Authentifizierung](https://go.microsoft.com/fwlink/?LinkId=232458) .  
  
## <a name="iis-hosted-services"></a>IIS-gehostete Dienste  

 Legen Sie für IIS-gehostete Dienste die Authentifizierungsschemas fest, die Sie in IIS verwenden möchten. Geben Sie dann in der web.config-Datei Ihres Diensts in der Bindungs Konfiguration den clientCredential-Typ als "erertierungsfromhost" an, wie im folgenden XML-Code Ausschnitt gezeigt:  
  
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
  
 Sie können angeben, dass nur eine Teilmenge der Authentifizierungs Schemas mit dem Dienst mithilfe von ServiceAuthenticationBehavior oder dem-Element verwendet werden soll \<serviceAuthenticationManager> . Beim Konfigurieren im Code verwenden Sie ServiceAuthenticationBehavior wie im folgenden Codeausschnitt dargestellt.  
  
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
  
 Wenn Sie dies in einer Konfigurationsdatei konfigurieren, verwenden Sie das- \<serviceAuthenticationManager> Element, wie im folgenden XML-Ausschnitt gezeigt.  
  
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
  
 Dadurch wird sichergestellt, dass nur eine Teilmenge der hier aufgeführten Authentifizierungsschemas für den Dienstendpunkt infrage kommt, je nachdem, was in IIS ausgewählt wurde. Dies bedeutet, dass ein Entwickler z. B. die Standardauthentifizierung aus der Liste ausschließen kann, indem er sie in der serviceAuthenticationManager-Liste auslässt. Sie wird auch nicht auf den Dienstendpunkt angewendet, wenn sie in IIS aktiviert ist.  
  
## <a name="self-hosted-services"></a>Selbst gehostete Dienste  

 Selbst gehostete Dienste werden geringfügig anders konfiguriert, da keine Einstellungen von IIS geerbt werden können. Hier verwenden Sie das- \<serviceAuthenticationManager> Element oder ServiceAuthenticationBehavior, um die Authentifizierungs Einstellungen anzugeben, die vererbt werden. Der Code sieht folgendermaßen aus:  
  
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
  
 In der config-Datei sieht das wie folgt aus:  
  
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
  
 Außerdem können Sie InheritFromHost in den Bindungseinstellungen angeben, wie im folgenden XML-Ausschnitt gezeigt.  
  
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
  
 Alternativ können Sie die Authentifizierungsschemas in einer benutzerdefinierten Bindung angeben, indem Sie die Authentifizierungsschemas für das HTTP-Transportbindungselement festlegen, wie im folgenden Konfigurationsausschnitt dargestellt.  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Bindungen und Sicherheit](bindings-and-security.md)
- [Endpunkte: Adressen, Bindungen und Verträge](endpoints-addresses-bindings-and-contracts.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](configuring-system-provided-bindings.md)
- [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](security-capabilities-with-custom-bindings.md)
- [Bindungen](bindings.md)
- [Benutzerdefinierte Bindungen](../extending/custom-bindings.md)
