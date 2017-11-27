---
title: PeerSecuritySettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 02cd483f2f7ec5e599b286b672d051a0e8d57940
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="peersecuritysettings"></a>PeerSecuritySettings
PeerSecuritySettings  
  
## <a name="syntax"></a>Syntax  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die PeerSecuritySettings-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die PeerSecuritySettings-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="mode"></a>Modus  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ob Sicherheit auf Nachrichtenebene und auf Transportebene von einem Endpunkt genutzt wird, der mit der Bindung konfiguriert wurde.  
  
### <a name="transport"></a>Transport  
 Datentyp: PeerTransportSecuritySettings  
  
 Zugriffstyp: Schreibgeschützt  
  
 Transportsicherheitseinstellungen.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.PeerSecuritySettings>
