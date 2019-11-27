---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 924d68dd828622b74c5e424a695f80874391b453
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430339"
---
# <a name="mexhttpsbinding"></a>\<mexhttpsbinding >
Gibt die Einstellungen für eine Bindung an, die für den WS-MetadataExchange-Nachrichtenaustausch (WS-MEX) über HTTPS verwendet wird.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexhttpsbinding >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<mexHttpsBinding>
  <binding closeTimeout="TimeSpan"
            name="string"
            openTimeout="TimeSpan"
            receiveTimeout="TimeSpan"
            sendTimeout="TimeSpan">
  </binding>
</mexHttpsBinding>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`closeTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|`name`|Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält. Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird. Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`openTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|`receiveTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:10:00.|  
|`sendTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 None.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Bindungen >](bindings.md)|Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Bindung ist im Grunde eine `WSHttpBinding`-Bindung, die mit Zertifikaten Sicherheit auf Transportebene unterstützt. Weitere Informationen zum Konfigurieren und Verwenden eines solchen Metadatenendpunkts finden Sie unter Gewusst [wie: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange Bindung](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), Gewusst [wie: Abrufen von Metadaten über eine nicht-MEX-Bindung](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)und das Beispiel für einen [benutzerdefinierten sicheren Metadatenendpunkt](../../../wcf/samples/custom-secure-metadata-endpoint.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange-Bindung](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [Vorgehensweise: Abrufen von Metadaten über eine Nicht-MEX-Bindung](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [Benutzerdefinierter sicherer Metadatenendpunkt](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [Metadaten](../../../wcf/feature-details/metadata.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Bindungs >](bindings.md)
