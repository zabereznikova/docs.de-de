---
title: ICLRValidator-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
ms.openlocfilehash: e071f9cba7e991c59bf697647e0e4badea57573a
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762039"
---
# <a name="iclrvalidator-interface"></a>ICLRValidator-Schnittstelle
Stellt Methoden zum Überprüfen von PE-Images (portable ausführbare Dateien) und zum Melden von Validierungs Fehlern bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[FormatEventInfo-Methode](iclrvalidator-formateventinfo-method.md)|Ruft eine ausführliche Meldung über den angegebenen Validierungs Fehler ab.|  
|[Validate-Methode](iclrvalidator-validate-method.md)|Überprüft die portable ausführbare Datei oder Microsoft Intermediate Language (MSIL) in der angegebenen Datei.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** IValidator. idl, IValidator. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRErrorReportingManager-Schnittstelle](iclrerrorreportingmanager-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
- [CLRRuntimeHost-Co-Klasse](clrruntimehost-coclass.md)
