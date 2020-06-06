---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7aa3755be97a839cb576d53852b75cfe50e39276
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "72773946"
---
# \<client>
Das `client`-Element definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**

## <a name="syntax"></a>Syntax

```xml
<system.serviceModel>
  <client>
    <endpoint>
    </endpoint>
    <metadata>
    </metadata>
  </client>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute
 Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[\<endpoint>](endpoint-of-client.md)|Enthält eine Auflistung von Endpunkt Elementen, mit denen die Endpunkte angegeben werden, mit denen dieser Client eine Verbindung herstellen kann.|
|[\<metadata>](metadata.md)|Enthält Einstellungen zum Verarbeiten von Metadaten.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|BESCHREIBUNG|
|-------------|-----------------|
|[\<system.serviceModel>](system-servicemodel.md)|Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.|

## <a name="remarks"></a>Bemerkungen
 Der `client`-Abschnitt definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann. Jeder im Clientabschnitt aufgeführte Endpunkt definiert seine eigene Bindung, sein eigenes Verhalten und seinen eigenen Vertrag. Er wird eindeutig anhand der Kombination des `name`-Attributs mit dem `contract`-Attribut identifiziert. Der Clientcode gibt den `name` an, um eine Verbindung zu einem Endpunkt für den durch den Client implementierten Dienst herzustellen. Wenn das `name`-Attribut ausgelassen wird, fungiert der Endpunkt als Standardendpunkt für den Vertrag, den er implementiert.

 Darüber hinaus gibt dieser Abschnitt auch die Einstellungen zum Verarbeiten von Metadaten an.

## <a name="example"></a>Beispiel

```xml
<client>
  <endpoint address="/HelloWorld/"
            bindingConfiguration="usingDefaults"
            name="MyBinding"
            binding="customBinding"
            contract="HelloWorld">
    <addressProperties actingAs="http://www.microsoft.com/TestActor"
                       identityData="BasicReadWrite"
                       identityType="Spn"
                       isAddressPrivate="false">
  </endpoint>
</client>
```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [WCF-Clientkonfiguration](../../../wcf/feature-details/client-configuration.md)
- [Clients](../../../wcf/feature-details/clients.md)
