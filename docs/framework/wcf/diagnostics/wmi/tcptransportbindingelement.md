---
title: TcpTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 180e954661319cb32edfd3180418fe9b1571ea5c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="tcptransportbindingelement"></a>TcpTransportBindingElement
TcpTransportBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Von der TcpTransportBindingElement-Klasse werden keine Methoden definiert.  
  
## <a name="properties"></a>Eigenschaften  
 Die TcpTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="connectionpoolsettings"></a>ConnectionPoolSettings  
 Datentyp: TcpConnectionPoolSettings  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Verbindungspooleinstellungen.  
  
### <a name="listenbacklog"></a>ListenBacklog  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Maximal mögliche Anzahl der ausstehenden Verbindungsanforderungen in der Warteschlange.  
  
### <a name="portsharingenabled"></a>PortSharingEnabled  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Boolescher Wert, der angibt, ob die TCP-Portfreigabe für diese Verbindung aktiviert ist.  
  
### <a name="teredoenabled"></a>TeredoEnabled  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Boolescher Wert, der angibt, ob das Teredo-Protokoll aktiviert ist, das zur Adressierung von Clients hinter einer Firewall verwendet wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
