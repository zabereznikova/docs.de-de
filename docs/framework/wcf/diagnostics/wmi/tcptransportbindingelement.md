---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: e64f689923d95546c8cecdf47c247faf79242ebf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485789"
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
