---
title: PrivacyNoticeBindingElement
ms.date: 03/30/2017
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
ms.openlocfilehash: 4bdd860304c73771933d0f8500c6003ac7692aa1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639509"
---
# <a name="privacynoticebindingelement"></a>PrivacyNoticeBindingElement
PrivacyNoticeBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class PrivacyNoticeBindingElement : BindingElement  
{  
  sint32 PrivacyNoticeVersion;  
  string Url;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die PrivacyNoticeBindingElement-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die PrivacyNoticeBindingElement-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="privacynoticeversion"></a>PrivacyNoticeVersion  
 Datentyp: sint32  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Version des Datenschutzhinweises  
  
### <a name="url"></a>URL  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die URL, an der sich der Datenschutzhinweis befindet.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
