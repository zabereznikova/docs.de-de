---
title: '&lt;Dienst&gt;'
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: a73e4699e0998338f09e1ed0504f5b1cfd73b225
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicegt"></a>&lt;Dienst&gt;
Das `service`-Element enthält die Einstellungen für einen Windows Communication Foundation (WCF)-Dienst. Es enthält außerdem Endpunkte, die den Dienst verfügbar machen.  
  
 \<system.ServiceModel>  
\<Services >  
\<Dienst >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<service behaviorConfiguration=String"  
        name="String"  
</service>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|behaviorConfiguration|Eine Zeichenfolge mit dem Namen des Verhaltens, das zum Instanziieren des Diensts verwendet werden soll. Der Verhaltensname muss sich bei der Dienstdefinition im Gültigkeitsbereich befinden. Der Standardwert ist eine leere Zeichenfolge.|  
|Name|Erforderliches Zeichenfolgenattribut, das den Typ des zu instanziierenden Diensts angibt. Diese Einstellung muss einem gültigen Typ entsprechen. Das Format muss `Namespace.Class.` lauten.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Endpunkt >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|Eine Auflistung von `endpoint`-Elementen, die diesen Dienst verfügbar machen.|  
|[\<Host >](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Gibt den Host dieser Dienstinstanz an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.HostElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|Das Stammelement aller WCF-Konfigurationselemente.|  
  
## <a name="remarks"></a>Hinweise  
 Dienste werden im `services`-Abschnitt der Konfigurationsdatei definiert. Eine Assembly kann eine beliebige Anzahl von Diensten enthalten. Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt. Dieser Abschnitt und sein Inhalt definieren den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.  
  
 Das `behaviorConfiguration`-Element ist optional. Es identifiziert das vom Dienst verwendete Verhalten. Das in diesem Attribut angegebene Verhalten muss mit einem Verhalten im Gültigkeitsbereich der gleichen Konfigurationsdatei verknüpft sein.  
  
 Jeder Dienst macht einen oder mehrere Endpunkte verfügbar, der über seine eigene Adresse und Bindung verfügt. Alle Bindungen innerhalb der Konfigurationsdatei müssen im Gültigkeitsbereich der Datei definiert sein. Bindungen sind durch die Kombination aus `name`-Attribut und `bindingConfiguration`-Attribut mit Endpunkten verknüpft. Das `name`-Attribut beschreibt, in welchem Abschnitt die Bindung definiert ist. Das `bindingConfiguration`-Attribut legt fest, welche Konfiguration innerhalb des Bindungsabschnitts verwendet wird. Ein Bindungsabschnitt kann verschiedene Konfigurationen definieren.  
  
## <a name="example"></a>Beispiel  
 Dies ist ein Beispiel für eine Dienstkonfiguration.  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"   
     name="HelloWorld">  
     <endpoint   
        address="/HelloWorld2/"  
        name="test"  
        bindingNamespace="http://www.cohowinery.com/"  
        binding="basicHttpBinding"  
        contract="IHelloWorld" />  
</service>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ServiceElement>  
 [Konfigurieren von Diensten](../../../../../docs/framework/wcf/configuring-services.md)
