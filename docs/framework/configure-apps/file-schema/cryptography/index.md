---
title: Schema für Kryptografieeinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
ms.openlocfilehash: c632a15552c8ba5743aac1309098b7d7ef949bbd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088005"
---
# <a name="cryptography-settings-schema"></a>Schema für Kryptografieeinstellungen
Das Schema für Kryptografieeinstellungen enthält Elemente, die angeben, wie die Anzeigenamen von Algorithmen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)

|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[**\<cryptoClasses**>](cryptoclasses-element.md)|Enthält eine Liste von Kryptografieklassen, die eine Zuordnung zu einem anzeigen Amen im- **\<nameEntry>** Element aufweisen.|  
|[**\<cryptoClass**>](cryptoclass-element.md)|Enthält eine Kryptografieklasse, die eine Zuordnung zu einem anzeigen Amen im- **\<nameEntry>** Element aufweist.|  
|[**\<cryptographySettings**>](cryptographysettings-element.md)|Enthält Kryptografieeinstellungen.|  
|[**\<cryptoNameMapping**>](cryptonamemapping-element.md)|Enthält die Zuordnung von Klassen zu den Anzeigenamen.|  
|[**\<mscorlib>**-Element für Kryptografieeinstellungen](mscorlib-element-for-cryptography-settings.md)|Enthält das- **\<cryptographySettings>** Element.|  
|[**\<nameEntry>**](nameentry-element.md)|Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.|  
|[**\<oidEntry>**](oidentry-element.md)|Ordnet einen ASN.1-Objektbezeichner (OID) einem Anzeigenamen zu.|  
|[**\<oidMap>**](oidmap-element.md)|Enthält die ASN.1-OID-Zuordnungen zu Klassen.|  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema](../index.md)
- [Kryptografiedienste](../../../../standard/security/cryptographic-services.md)
