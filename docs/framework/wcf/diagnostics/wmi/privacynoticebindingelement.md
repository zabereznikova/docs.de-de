---
title: PrivacyNoticeBindingElement
ms.date: 03/30/2017
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
ms.openlocfilehash: c6ebb585454054ca9a03c46cf738001c58f9b18e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273411"
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
  
### <a name="url"></a>url  

 Datentyp: String  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die URL, an der sich der Datenschutzhinweis befindet.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
