---
title: ICorRuntimeHost::CreateEvidence-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
ms.openlocfilehash: 264f16fc9e767584229376e67f5aee6db1069025
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501611"
---
# <a name="icorruntimehostcreateevidence-method"></a>ICorRuntimeHost::CreateEvidence-Methode
Ruft einen Schnittstellen Zeiger vom Typ ab <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> , mit dem der Host Sicherheits Beweise erstellen kann, die an die Methode " [kreatedomain](icorruntimehost-createdomain-method.md) " oder " [kreatedomainex](icorruntimehost-createdomainex-method.md) " übergeben werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pEvidence`  
 vorgenommen Ein Schnittstellen Zeiger auf eine- <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> Instanz, mit der Sicherheits Beweise erstellt werden. Dieser Zeiger ist typisiert `IUnknown` , sodass Aufrufer in der Regel `QueryInterface` für diese Schnittstelle aufgerufen werden, um einen Zeiger auf eine zu erhalten <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Der Vorgang wurde durchgeführt.|  
|S_FALSE|Der Vorgang konnte nicht ausgeführt werden.|  
|E_FAIL|Ein unbekannter, schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, ist die Common Language Runtime (CLR) im Prozess nicht mehr verwendbar. Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.|  
|HOST_E_CLRNOTAVAILABLE|Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Methode gibt eine leere Auflistung zurück, die nicht aus nativem Code aufgefüllt werden kann. Verwenden Sie stattdessen die- <xref:System.Security.Policy.Evidence> Methode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Version:** 1,0, 1,1  
  
## <a name="see-also"></a>Weitere Informationen:

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [ICorRuntimeHost-Schnittstelle](icorruntimehost-interface.md)
