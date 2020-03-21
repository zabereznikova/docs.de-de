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
ms.openlocfilehash: 0f5bdf97132c05e765cd6fa423a19bb996105d28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175264"
---
# <a name="imetadatainfogetfilemapping-method"></a>IMetaDataInfo::GetFileMapping-Methode
Ruft den Speicherbereich der zugeordneten Datei und den Zuordnungstyp ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,
    [out] ULONGLONG            *pcbData,
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppvData`  
 [out] Ein Zeiger auf den Anfang der zugeordneten Datei.  
  
 `pcbData`  
 [out] Die Größe des zugeordneten Bereichs. Wenn `pdwMappingType` `fmFlat`dies der Falle ist, ist dies die Größe der Datei.  
  
 `pdwMappingType`  
 [out] Ein [CorFileMapping-Wert,](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) der den Zuordnungstyp angibt. Die aktuelle Implementierung der Common Language Runtime `fmFlat`(CLR) gibt immer zurück. Andere Werte sind für die zukünftige Verwendung reserviert. Sie sollten jedoch immer den zurückgegebenen Wert überprüfen, da andere Werte in zukünftigen Versionen oder Dienstversionen aktiviert werden können.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|Alle Ausgänge sind gefüllt.|  
|`E_INVALIDARG`|NULL wurde als Argumentwert übergeben.|  
|`COR_E_NOTSUPPORTED`|Die CLR-Implementierung kann keine Informationen über den Speicherbereich bereitstellen. Dies kann aus folgenden Gründen geschehen:<br /><br /> - Der Metadatenbereich wurde `ofWrite` `ofCopyMemory` mit dem oder-Flag geöffnet.<br />- Der Metadatenbereich wurde `ofReadOnly` ohne das Flag geöffnet.<br />- Die [IMetaDataDispenser::OpenScopeOnMemory-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) wurde verwendet, um nur den Metadatenteil der Datei zu öffnen.<br />- Die Datei ist keine portable ausführbare Datei (PE). **Hinweis:**  Diese Bedingungen hängen von der CLR-Implementierung ab und werden wahrscheinlich in zukünftigen Versionen der CLR geschwächt.|  
  
## <a name="remarks"></a>Bemerkungen  
 Der Speicher, auf den verweist, `ppvData` ist nur gültig, solange der zugrunde liegende Metadatenbereich geöffnet ist.  
  
 Damit diese Methode funktioniert, müssen Sie beim Zuordnen der Metadaten einer On-Disk-Datei in den Speicher die [IMetaDataDispenser::OpenScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) angeben, `ofReadOnly` und Sie dürfen das `ofWrite` oder-Flag `ofCopyMemory` nicht angeben.  
  
 Die Auswahl des Dateizuordnungstyps für jeden Bereich ist spezifisch für eine bestimmte Implementierung der CLR. Sie kann vom Benutzer nicht festgelegt werden. Die aktuelle Implementierung der CLR `pdwMappingType`gibt immer in zurück, `fmFlat` dies kann sich jedoch in zukünftigen Versionen der CLR oder in zukünftigen Service-Releases einer bestimmten Version ändern. Sie sollten den zurückgegebenen `pdwMappingType`Wert immer in überprüfen, da verschiedene Typen unterschiedliche Layouts und Offsets aufweisen.  
  
 Das Übergeben von NULL für einen der drei Parameter wird nicht unterstützt. Die Methode `E_INVALIDARG`gibt zurück, und keine ausgabe wird gefüllt. Das Ignorieren des Zuordnungstyps oder der Größe der Region kann zu einer ungewöhnlichen Programmbeendigung führen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [CorFileMapping-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
