---
title: ICorRuntimeHost::GetDefaultDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetDefaultDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type:
- apiref
ms.openlocfilehash: 673c32c86c808c36db6454b8a9f0d8e68f9b1258
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720632"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a>ICorRuntimeHost::GetDefaultDomain-Methode

Ruft einen Schnittstellen Zeiger vom Typ ab <xref:System._AppDomain?displayProperty=nameWithType> , der die Standard Domäne für den aktuellen Prozess darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pAppDomain`  
 vorgenommen Ein Schnittstellen Zeiger vom Typ <xref:System._AppDomain?displayProperty=nameWithType> für die- <xref:System.AppDomain> Instanz, die die Standard Anwendungsdomäne für den Prozess darstellt.  
  
 Dieser Zeiger ist typisiert. `IUnknown` daher sollten Aufrufer im allgemeinen aufzurufen, `QueryInterface` um einen Schnittstellen Zeiger vom Typ zu erhalten <xref:System._AppDomain?displayProperty=nameWithType> .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Der Vorgang wurde durchgeführt.|  
|S_FALSE|Der Vorgang konnte nicht ausgeführt werden.|  
|E_FAIL|Ein unbekannter, schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die Common Language Runtime (CLR) im Prozess nicht mehr verwendbar. Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:** 1,0, 1,1  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [ICorRuntimeHost-Schnittstelle](icorruntimehost-interface.md)
