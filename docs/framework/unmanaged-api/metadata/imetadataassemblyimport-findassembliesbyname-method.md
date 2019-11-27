---
title: IMetaDataAssemblyImport::FindAssembliesByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
ms.openlocfilehash: c12d3a7a7d1e52529435361aa12e22e4edeecf03
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448290"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>IMetaDataAssemblyImport::FindAssembliesByName-Methode
Ruft ein Array von Assemblys mit dem angegebenen `szAssemblyName`-Parameter ab und verwendet dabei die Standardregeln, die vom Common Language Runtime (CLR) zum Auflösen von Verweisen verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,   
    [in]  LPCWSTR     szPrivateBin,   
    [in]  LPCWSTR     szAssemblyName,   
    [out] IUnknown    *ppIUnk[],   
    [in]  ULONG       cMax,   
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `szAppBase`  
 in Das Stammverzeichnis, in dem nach der angegebenen Assembly gesucht werden soll. Wenn dieser Wert auf `null`festgelegt ist, sucht `FindAssembliesByName` nur im globalen Assemblycache für die Assembly.  
  
 `szPrivateBin`  
 in Eine Liste von durch Semikolons getrennten Unterverzeichnissen (z. b. "bin; BIN2") unter dem Stammverzeichnis, in dem nach der Assembly gesucht werden soll. Diese Verzeichnisse werden zusätzlich zu den in den standardmäßigen Prüfregeln angegebenen Verzeichnissen geprüft.  
  
 `szAssemblyName`  
 in Der Name der zu suchenden Assembly. Das Format dieser Zeichenfolge wird auf der Klassen Verweisseite für <xref:System.Reflection.AssemblyName>definiert.  
  
 `ppIUnk`  
 in Ein Array vom Typ [IUnknown](/cpp/atl/iunknown) , in das die `IMetadataAssemblyImport` Schnittstellen Zeiger eingefügt werden sollen.  
  
 `cMax`  
 vorgenommen Die maximale Anzahl von Schnittstellen Zeigern, die in `ppIUnk`platziert werden können.  
  
 `pcAssemblies`  
 vorgenommen Die Anzahl der zurückgegebenen Schnittstellen Zeiger. Das heißt, die Anzahl der Schnittstellen Zeiger, die tatsächlich in `ppIUnk`platziert werden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName` erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine Assemblys vorhanden.|  
  
## <a name="remarks"></a>Hinweise  
 Bei Angabe eines Assemblynamens findet die `FindAssembliesByName`-Methode die Assembly anhand der Standardregeln zum Auflösen von Assemblyverweisen. (Weitere Informationen finden Sie unter [so](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)sucht Common Language Runtime nach Assemblys.) `FindAssembliesByName` ermöglicht es dem Aufrufer, verschiedene Aspekte des Assemblyresolverkontexts zu konfigurieren, z. b. Anwendungs Basis und privater Suchpfad.  
  
 Die `FindAssembliesByName`-Methode erfordert, dass die CLR im Prozess initialisiert wird, um die Assemblyauflösungs-Logik aufzurufen. Daher müssen Sie vor dem Aufrufen von `FindAssembliesByName`[CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (Übergabe COINITEE_DEFAULT) aufrufen und dann mit einem Aufruf von " [dininitializecor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)" folgen.  
  
 `FindAssembliesByName` gibt einen [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -Zeiger auf die Datei zurück, die das Assemblymanifest für den weiter gegebenen Assemblynamen enthält. Wenn der angegebene Assemblyname nicht vollständig angegeben ist (z. b. wenn er keine Version enthält), werden möglicherweise mehrere Assemblys zurückgegeben.  
  
 `FindAssembliesByName` wird häufig von einem Compiler verwendet, der versucht, eine referenzierte Assembly zur Kompilierzeit zu finden.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [So sucht Common Language Runtime nach Assemblys](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
