---
title: IMetaDataInfo::GetFileMapping-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84d53bd5bb9c0eca83b39fc9d1c83d93440e336b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645465"
---
# <a name="imetadatainfogetfilemapping-method"></a>IMetaDataInfo::GetFileMapping-Methode
Ruft den Arbeitsspeicherbereich von der zugeordneten Datei und den Typ der Zuordnung ab.  
  
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
 [out] Ein [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) Wert, der den Typ der Zuordnung angibt. Die aktuelle Implementierung der common Language Runtime (CLR) gibt immer `fmFlat`. Andere Werte sind für die zukünftige Verwendung reserviert. Allerdings sollten Sie den zurückgegebenen Wert, immer überprüfen, da andere Werte werden, in zukünftigen Versionen aktiviert können oder service Releases.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|Alle Ausgaben werden aufgefüllt.|  
|`E_INVALIDARG`|NULL wurde als Argumentwert übergeben.|  
|`COR_E_NOTSUPPORTED`|Die CLR-Implementierung kann keine Informationen zu den Arbeitsspeicherbereich bieten. Dies kann aus den folgenden Gründen geschehen:<br /><br /> – Der Metadatenbereich wurde geöffnet, mit der `ofWrite` oder `ofCopyMemory` Flag.<br />-Der Metadatenbereich geöffnet wurde, ohne die `ofReadOnly` Flag.<br />– Die [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) Methode wurde verwendet, um nur die Metadatenteil der Datei zu öffnen.<br />-Die Datei ist keiner PE (portable Executable)-Datei. **Hinweis**:  Diese Bedingungen hängen von der CLR-Implementierung, und Sie werden wahrscheinlich in zukünftigen Versionen der CLR herabgesetzt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Der Arbeitsspeicher, `ppvData` verweist, ist gültig, nur so lange im zugrunde liegenden Metadatenbereich geöffnet ist.  
  
 In der Reihenfolge für diese Methode funktioniert, wenn Sie die Metadaten einer Datei auf dem Datenträger durch den Aufruf in den Arbeitsspeicher zuordnen die [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) -Methode, die Sie angeben müssen die `ofReadOnly` Flag und Sie müssen nicht angeben. die `ofWrite` oder `ofCopyMemory` Flag.  
  
 Die Auswahl der Zuordnung der Dateityp für jeden Bereich bezieht sich auf eine Implementierung der CLR. Es kann nicht vom Benutzer festgelegt werden. Gibt die aktuelle Implementierung der CLR immer `fmFlat` in `pdwMappingType`, aber dies kann sich in zukünftigen Versionen der CLR oder in Zukunft Service Releases von einer bestimmten Version ändern. Sie sollten immer den zurückgegebenen Wert überprüfen, `pdwMappingType`, da verschiedene Typen unterschiedliche Layouts und Offsets haben.  
  
 Übergeben NULL für eine beliebige der drei Parameter wird nicht unterstützt. Gibt die Methode zurück `E_INVALIDARG`, und keine Ausgabe wird ausgefüllt. Ignorieren den Zuordnungstyp oder die Größe des Bereichs kann dazu führen, dass nicht normale programmbeendigung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [CorFileMapping-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
