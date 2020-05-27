---
title: IMetaDataAssemblyEmit::SetAssemblyProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
ms.openlocfilehash: 7c6adcbcfe64f63048078b4ccba6727a58531033
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008104"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a>IMetaDataAssemblyEmit::SetAssemblyProps-Methode
Ändert die angegebene `Assembly`-Metadatenstruktur.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pma`  
 in Das Metadatentoken, das die `Assembly` zu ändernde Metadatenstruktur angibt.  
  
 `pbPublicKey`  
 in Ein Zeiger auf den öffentlichen Schlüssel des Verlegers der Assembly.  
  
 `cbPublicKey`  
 in Die Größe von in Bytes `pbPublicKey` .  
  
 `ulHashAlgId`  
 in Der Bezeichner für den Hash Algorithmus, der zum Hash der Assemblydateien verwendet wird.  
  
 `szName`  
 in Der lesbare Textname der Assembly.  
  
 `pMetaData`  
 in Ein Zeiger auf die ASSEMBLYMETADATA, die Informationen zu Version, Plattform und Gebiets Schema für die Assembly enthält.  
  
 `dwAssemblyFlags`  
 in Eine bitweise Kombination von [AssemblyFlags](assemblyflags-enumeration.md) -Werten, die verschiedene Attribute der Assembly angeben.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Erstellen einer `Assembly` Metadatenstruktur die [IMetaDataAssemblyEmit::D efineassembly](imetadataassemblyemit-defineassembly-method.md) -Methode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
