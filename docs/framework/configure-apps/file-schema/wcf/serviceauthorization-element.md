---
title: '&lt;serviceAuthorization&gt;-Element'
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: 6c69d10eb2f6cdf4546dd5895d196723417f5494
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146003"
---
# <a name="ltserviceauthorizationgt-element"></a>&lt;serviceAuthorization&gt;-Element
Gibt Einstellungen an, die den Zugriff auf Dienstvorgänge autorisieren.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<Verhalten >  
\<ServiceAuthorization >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|impersonateCallerForAllOperations|Ein boolescher Wert, der angibt, ob alle Vorgänge im Dienst die Identität des Aufrufers annehmen. Die Standardeinstellung ist `false`.<br /><br /> Wenn ein bestimmter Dienstvorgang die Identität des Aufrufers annimmt, wird der Threadkontext zum Aufruferkontext geändert, bevor der angegebene Dienst ausgeführt wird.|  
|principalPermissionMode|Legt den Prinzipal fest, der verwendet wird, um Vorgänge auf dem Server auszuführen. Folgende Werte sind gültig:<br /><br /> – None<br />-UseWindowsGroups<br />-UseAspNetRoles<br />-Custom<br /><br /> Der Standardwert ist UseWindowsGroups. Der Wert ist vom Typ <xref:System.ServiceModel.Description.PrincipalPermissionMode>. Weitere Informationen zur Verwendung dieses Attributs finden Sie unter [Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).|  
|roleProviderName|Eine Zeichenfolge, die den Namen des Rollenanbieters angibt, der Rolleninformationen für eine Windows Communication Foundation (WCF)-Anwendung bereitstellt. Der Standardwert ist eine leere Zeichenfolge.|  
|ServiceAuthorizationManagerType|Eine Zeichenfolge, die den Typ des Dienstautorisierungs-Managers angibt. Weitere Informationen finden Sie unter <xref:System.ServiceModel.ServiceAuthorizationManager>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|authorizationPolicies|Enthält eine Auflistung der Autorisierungsrichtlinien-Typen, die mithilfe des `add`-Schlüsselworts hinzugefügt werden können. Jede Autorisierungsrichtlinie enthält ein einziges erforderliches `policyType`-Attribut, bei dem es sich um eine Zeichenfolge handelt. Das Attribut gibt eine Autorisierungsrichtlinie an, die die Transformation einer Gruppe von Eingabeansprüchen in eine andere Gruppe von Eingabeansprüchen ermöglicht. Die Zugriffssteuerung kann basierend darauf gewährt oder verweigert werden. Weitere Informationen finden Sie unter <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Enthält eine Auflistung der Einstellungen für das Verhalten eines Diensts.|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Abschnitt enthält Elemente, die die Autorisierung, benutzerspezifische Rollenanbieter und den Identitätswechsel beeinflussen.  
  
 Das `principalPermissionMode`-Attribut gibt die Benutzergruppen an, mit denen die Verwendung einer geschützten Methode autorisiert wird. Der Standardwert lautet `UseWindowsGroups`. Er gibt an, das in Windows-Gruppen wie "Administratoren" oder "Benutzer" nach einer Identität gesucht wird, die versucht, auf eine Ressource zuzugreifen. Sie können auch angeben `UseAspNetRoles` einen benutzerdefinierten Rollenanbieter, der unter konfiguriert ist, verwenden die \<system.web > Element, wie im folgenden Code dargestellt.  
  
```xml  
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
           type="System.Web.Security.SqlMembershipProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipProvider"
           enablePasswordRetrieval="false"
           enablePasswordReset="false"
           requiresQuestionAndAnswer="false"
           requiresUniqueEmail="true"
           passwordFormat="Hashed" />
    </providers>
  </membership>
  <!-- Other configuration code not shown. -->
</system.web>
```  
  
 Im folgenden Code wird `roleProviderName` mit dem `principalPermissionMode`-Attribut verwendet.  
  
```xml  
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```  
  
 Ein ausführliches Beispiel für die Verwendung dieses Konfigurationselements finden Sie unter [Zugriff auf Dienstvorgänge autorisieren](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) und [Autorisierungsrichtlinie](../../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Zugriffsautorisierung für Dienstvorgänge](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 [Autorisierungsrichtlinie](../../../../../docs/framework/wcf/samples/authorization-policy.md)
