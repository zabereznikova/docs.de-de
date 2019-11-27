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
ms.openlocfilehash: 0cd2071d4410615a08e774ba30e0e8fe8d1fa7c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436177"
---
# <a name="imetadatainfogetfilemapping-method"></a>IMetaDataInfo::GetFileMapping-Methode
Ruft den Speicherbereich der zugeordneten Datei und den Typ der Zuordnung ab.  
  
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
 vorgenommen Ein Zeiger auf den Anfang der zugeordneten Datei.  
  
 `pcbData`  
 vorgenommen Die Größe des zugeordneten Bereichs. Wenn `pdwMappingType` `fmFlat`ist, ist dies die Größe der Datei.  
  
 `pdwMappingType`  
 vorgenommen Ein [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) -Wert, der den Typ der Zuordnung angibt. Die aktuelle Implementierung des Common Language Runtime (CLR) gibt immer `fmFlat`zurück. Andere Werte sind für die zukünftige Verwendung reserviert. Sie sollten jedoch immer den zurückgegebenen Wert überprüfen, weil andere Werte möglicherweise in zukünftigen Versionen oder Dienst Releases aktiviert werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|Alle Ausgaben werden aufgefüllt.|  
|`E_INVALIDARG`|NULL wurde als Argument Wert übermittelt.|  
|`COR_E_NOTSUPPORTED`|Die CLR-Implementierung kann keine Informationen über die Speicher Region bereitstellen. Dafür können die folgenden Gründe verantwortlich sein:<br /><br /> -Der Metadatenbereich wurde mit dem `ofWrite`-oder `ofCopyMemory`-Flag geöffnet.<br />-Der Metadatenbereich wurde ohne das `ofReadOnly`-Flag geöffnet.<br />-Die [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) -Methode wurde verwendet, um nur den Metadatenteil der Datei zu öffnen.<br />-Die Datei ist keine portable ausführbare Datei (PE). **Hinweis:**  Diese Bedingungen sind von der CLR-Implementierung abhängig und werden wahrscheinlich in zukünftigen Versionen der CLR geschwächt.|  
  
## <a name="remarks"></a>Hinweise  
 Der Arbeitsspeicher, auf den `ppvData` verweist, ist nur gültig, solange der zugrunde liegende Metadatenbereich geöffnet ist.  
  
 Damit diese Methode funktioniert, müssen Sie, wenn Sie die Metadaten einer Datei auf dem Datenträger durch Aufrufen der [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) -Methode in den Arbeitsspeicher zuordnen, das `ofReadOnly`-Flag angeben, und Sie dürfen das `ofWrite` oder `ofCopyMemory`-Flag nicht angeben.  
  
 Die Auswahl des Datei Mapping-Typs für jeden Bereich ist spezifisch für eine bestimmte Implementierung der CLR. Er kann nicht vom Benutzer festgelegt werden. Die aktuelle Implementierung der CLR gibt immer `fmFlat` in `pdwMappingType`zurück. Dies kann sich jedoch in zukünftigen Versionen der CLR oder in zukünftigen Dienst Releases einer bestimmten Version ändern. Sie sollten den zurückgegebenen Wert immer in `pdwMappingType`überprüfen, da unterschiedliche Typen verschiedene Layouts und Offsets aufweisen werden.  
  
 Das übergeben von NULL für einen der drei Parameter wird nicht unterstützt. Die Methode gibt `E_INVALIDARG`zurück, und es werden keine Ausgaben aufgefüllt. Wenn Sie den Mapping-Typ oder die Größe des Bereichs ignorieren, kann dies zu einem ungewöhnlichen Programmabbruch führen.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [CorFileMapping-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
