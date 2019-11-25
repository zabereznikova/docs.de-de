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
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088005"
---
# <a name="cryptography-settings-schema"></a>Schema für Kryptografieeinstellungen
Das Schema für Kryptografieeinstellungen enthält Elemente, die angeben, wie die Anzeigenamen von Algorithmen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<mscorlib->** ](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptographySettings >** ](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoNameMapping**](cryptonamemapping-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**cryptoClasses**](cryptoclasses-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoClass >** ](cryptoclass-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<nameEntry >** ](nameentry-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<oidmap**](oidmap-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<oidEntry >** ](oidentry-element.md)

|Element|Beschreibung|  
|-------------|-----------------|  
|[ **\<cryptoClasses**>](cryptoclasses-element.md)|Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet sind.|  
|[ **\<cryptoClass**>](cryptoclass-element.md)|Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet ist.|  
|[ **\<cryptographySettings**>](cryptographysettings-element.md)|Enthält Kryptografieeinstellungen.|  
|[ **\<cryptoNameMapping**>](cryptonamemapping-element.md)|Enthält die Zuordnung von Klassen zu den Anzeigenamen.|  
|[ **\<mscorlib>** -Element für Kryptografieeinstellungen](mscorlib-element-for-cryptography-settings.md)|Enthält das Element **\<cryptographySettings>** .|  
|[ **\<nameEntry>** ](nameentry-element.md)|Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.|  
|[ **\<oidEntry>** ](oidentry-element.md)|Ordnet einen ASN.1-Objektbezeichner (OID) einem Anzeigenamen zu.|  
|[ **\<oidMap>** ](oidmap-element.md)|Enthält die ASN.1-OID-Zuordnungen zu Klassen.|  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema](../index.md)
- [Kryptografische Dienste](../../../../standard/security/cryptographic-services.md)
