---
title: Dienst
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: c59672b3b7617d9c28d99f7d534b6e7f2f2e9fbb
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2018
ms.locfileid: "49633942"
---
# <a name="service"></a>Dienst
Dienst  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die Dienstklasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die Dienstklasse hat die folgenden Eigenschaften:  
  
### <a name="baseaddresses"></a>BaseAddresses  
 Datentyp: Zeichenfolgenarray  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die vom Dienst verwendeten Basisadressen.  
  
### <a name="behaviors"></a>Verhalten  
 Datentyp: Behavior-Array  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die diesem Dienst zugewiesenen Verhalten.  
  
### <a name="configurationname"></a>ConfigurationName  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 ServiceElement_BehaviorConfiguration  
  
### <a name="counterinstancename"></a>CounterInstanceName  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Name der Instanz der Leistungsindikatoren des Dienstes.  
  
### <a name="distinguishedname"></a>DistinguishedName  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Dienstname an der Adresse.  
  
### <a name="extensions"></a>Erweiterungen  
 Datentyp: Zeichenfolgenarray  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Instanzkontexte für die Erweiterungen der Dienstinstanz.  
  
### <a name="metadata"></a>Metadaten  
 Datentyp: Zeichenfolgenarray  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Dienstmetadateneinstellungen.  
  
### <a name="name"></a>name  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der eindeutige Name des Diensts.  
  
### <a name="namespace"></a>Namespace  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Der Namespace des Dienstes.  
  
### <a name="opened"></a>Opened  
 Datentyp: Zeitpunkt (Datum und Uhrzeit)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Zeit, zu der der Dienst geöffnet wurde.  
  
### <a name="outgoingchannels"></a>OutgoingChannels  
 Data type: Channel array (Kanal-Array)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Kanäle, die von der Dienstinstanz ausgehen.  
  
### <a name="processid"></a>ProcessId  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Prozess-ID des Vorgangs, von dem der Dienst gehostet wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|
