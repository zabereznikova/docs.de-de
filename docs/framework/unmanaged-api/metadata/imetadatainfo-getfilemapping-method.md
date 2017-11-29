---
title: IMetaDataInfo::GetFileMapping-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataInfo.GetFileMapping
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 74f44d366ec4f3848f7c8436e208dcaee3466fe1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatainfogetfilemapping-method"></a>IMetaDataInfo::GetFileMapping-Methode
Ruft den Speicherbereich, der die zugeordnete Datei und den Typ der Zuordnung ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppvData`  
 [out] Ein Zeiger auf den Anfang der zugeordneten Datei.  
  
 `pcbData`  
 [out] Die Größe des zugeordneten Bereichs. Wenn `pdwMappingType` ist `fmFlat`, dies ist die Größe der Datei.  
  
 `pdwMappingType`  
 [out] Ein [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) Wert, der den Typ der Zuordnung angibt. Gibt immer die aktuelle Implementierung der common Language Runtime (CLR) `fmFlat`. Andere Werte sind für die zukünftige Verwendung reserviert. Allerdings sollten Sie immer den zurückgegebenen Wert überprüfen, da andere Werte möglicherweise in zukünftigen Versionen aktiviert oder service Releases.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|Alle Ausgaben werden aufgefüllt.|  
|`E_INVALIDARG`|NULL wurde als ein Wert des Arguments übergeben.|  
|`COR_E_NOTSUPPORTED`|Die CLR-Implementierung kann keine Informationen zu den Speicherbereich bereitstellen. Dies kann folgenden Ursachen haben:<br /><br /> -Die Metadatenbereich geöffnet wurde, mit der `ofWrite` oder `ofCopyMemory` Flag.<br />-Die Metadatenbereich geöffnet wurde, ohne die `ofReadOnly` Flag.<br />– Der [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) Methode wurde verwendet, um nur den Metadatenteil der Datei zu öffnen.<br />-Die Datei ist keine Datei PE (portable Executable). **Hinweis:** diese Bedingungen hängen von der CLR-Implementierung und sind wahrscheinlich abgeschwächt in zukünftigen Versionen der CLR.|  
  
## <a name="remarks"></a>Hinweise  
 Der Arbeitsspeicher, `ppvData` verweist, ist gültig, nur so lange im zugrunde liegenden Metadatenbereich geöffnet ist.  
  
 In der Reihenfolge für diese Methode funktioniert, wenn Sie durch Aufrufen der Metadaten einer Datei auf dem Datenträger in den Arbeitsspeicher zuordnen die [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) -Methode, die Sie angeben müssen die `ofReadOnly` Flag und Sie müssen nicht angeben der `ofWrite` oder `ofCopyMemory` Flag.  
  
 Die Auswahl der Zuordnung der Dateityp für die einzelnen Bereiche bezieht sich auf eine bestimmte Implementierung der CLR. Er kann nicht vom Benutzer festgelegt werden. Gibt die aktuelle Implementierung der CLR immer `fmFlat` in `pdwMappingType`, aber dies kann sich in zukünftigen Versionen der CLR oder zukünftigen Dienstversionen einer bestimmten Version ändern. Überprüfen Sie den zurückgegebenen Wert immer `pdwMappingType`, da verschiedene Typen unterschiedliche Layouts und Offsets haben.  
  
 Übergeben NULL für einen der drei Parameter wird nicht unterstützt. Gibt die Methode `E_INVALIDARG`, und dass keines der Ausgaben aufgefüllt werden. Ignorieren von Zuordnungstyp oder die Größe des Bereichs kann dazu führen, dass nicht normale programmbeendigung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 [CorFileMapping-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
