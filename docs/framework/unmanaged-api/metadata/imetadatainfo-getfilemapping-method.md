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
ms.openlocfilehash: 8823f3cc016072d3f20100c29532459da5e97492
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682389"
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
 vorgenommen Die Größe des zugeordneten Bereichs. Wenn `pdwMappingType` ist `fmFlat` , ist dies die Größe der Datei.  
  
 `pdwMappingType`  
 vorgenommen Ein [CorFileMapping](corfilemapping-enumeration.md) -Wert, der den Typ der Zuordnung angibt. Die aktuelle Implementierung des Common Language Runtime (CLR) gibt immer zurück `fmFlat` . Andere Werte sind für die zukünftige Verwendung reserviert. Sie sollten jedoch immer den zurückgegebenen Wert überprüfen, weil andere Werte möglicherweise in zukünftigen Versionen oder Dienst Releases aktiviert werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|Alle Ausgaben werden aufgefüllt.|  
|`E_INVALIDARG`|NULL wurde als Argument Wert übermittelt.|  
|`COR_E_NOTSUPPORTED`|Die CLR-Implementierung kann keine Informationen über die Speicher Region bereitstellen. Dies kann aus folgenden Gründen geschehen:<br /><br /> -Der Metadatenbereich wurde mit dem- `ofWrite` Flag oder dem- `ofCopyMemory` Flag geöffnet.<br />-Der Metadatenbereich wurde ohne das- `ofReadOnly` Flag geöffnet.<br />-Die [IMetaDataDispenser:: OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) -Methode wurde verwendet, um nur den Metadatenteil der Datei zu öffnen.<br />-Die Datei ist keine portable ausführbare Datei (PE). **Hinweis:**  Diese Bedingungen sind von der CLR-Implementierung abhängig und werden wahrscheinlich in zukünftigen Versionen der CLR geschwächt.|  
  
## <a name="remarks"></a>Hinweise  

 Der Arbeitsspeicher, `ppvData` auf den verweist, ist nur gültig, solange der zugrunde liegende Metadatenbereich geöffnet ist.  
  
 Damit diese Methode funktioniert, müssen Sie das-Flag angeben, wenn Sie die Metadaten einer Datei auf dem Datenträger durch Aufrufen der [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) -Methode im Arbeitsspeicher zuordnen, `ofReadOnly` und Sie dürfen das-Flag oder das-Flag nicht angeben `ofWrite` `ofCopyMemory` .  
  
 Die Auswahl des Datei Mapping-Typs für jeden Bereich ist spezifisch für eine bestimmte Implementierung der CLR. Er kann nicht vom Benutzer festgelegt werden. Die aktuelle Implementierung der CLR gibt immer `fmFlat` in zurück `pdwMappingType` , dies kann sich jedoch in zukünftigen Versionen der CLR oder in zukünftigen Dienst Releases einer bestimmten Version ändern. Sie sollten immer den zurückgegebenen Wert in überprüfen `pdwMappingType` , da unterschiedliche Typen verschiedene Layouts und Offsets aufweisen werden.  
  
 Das übergeben von NULL für einen der drei Parameter wird nicht unterstützt. Die-Methode gibt zurück `E_INVALIDARG` , und keine der Ausgaben wird ausgefüllt. Wenn Sie den Mapping-Typ oder die Größe des Bereichs ignorieren, kann dies zu einem ungewöhnlichen Programmabbruch führen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataInfo-Schnittstelle](imetadatainfo-interface.md)
- [CorFileMapping-Enumeration](corfilemapping-enumeration.md)
