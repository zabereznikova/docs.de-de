---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: 61eae75de04f75b6ad6e78d16569595732b3d28f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273307"
---
# <a name="securitybindingelement"></a>SecurityBindingElement

SecurityBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a>Methoden  

 Die SecurityBindingElement-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  

 Die SecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="defaultalgorithmsuite"></a>DefaultAlgorithmSuite  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt die Algorithmen an, die mit der Bindung verwendet werden sollen.  
  
### <a name="includetimestamp"></a>IncludeTimestamp  

 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob jede Nachricht einen Timestamp enthält.  
  
### <a name="keyentropymode"></a>KeyEntropyMode  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Entropiequelle zum Erstellen von Schlüsseln.  
  
### <a name="localservicesecuritysettings"></a>LocalServiceSecuritySettings  

 Datentyp: LocalServiceSecuritySettings  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die bindungsspezifischen Sicherheitseigenschaften für den lokalen Dienst.  
  
### <a name="messagesecurityversion"></a>MessageSecurityVersion  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die für Nachrichtensicherheit verwendete Version.  
  
### <a name="securityheaderlayout"></a>SecurityHeaderLayout  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Reihenfolge der Elemente im Sicherheitsheader für diese Bindung.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
