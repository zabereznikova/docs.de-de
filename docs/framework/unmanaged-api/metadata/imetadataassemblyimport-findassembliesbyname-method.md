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
ms.openlocfilehash: d2693a94f02214df6d7265b26e3d70d91adcf8a7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503834"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>IMetaDataAssemblyImport::FindAssembliesByName-Methode
Ruft ein Array von Assemblys mit dem angegebenen `szAssemblyName` Parameter ab und verwendet dabei die Standardregeln, die vom Common Language Runtime (CLR) zum Auflösen von Verweisen verwendet werden.  
  
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
 in Das Stammverzeichnis, in dem nach der angegebenen Assembly gesucht werden soll. Wenn dieser Wert auf festgelegt ist `null` , `FindAssembliesByName` sucht nur im globalen Assemblycache für die Assembly.  
  
 `szPrivateBin`  
 in Eine Liste von durch Semikolons getrennten Unterverzeichnissen (z. b. "bin; BIN2") unter dem Stammverzeichnis, in dem nach der Assembly gesucht werden soll. Diese Verzeichnisse werden zusätzlich zu den in den standardmäßigen Prüfregeln angegebenen Verzeichnissen geprüft.  
  
 `szAssemblyName`  
 in Der Name der zu suchenden Assembly. Das Format dieser Zeichenfolge wird auf der Klassen Verweisseite für definiert <xref:System.Reflection.AssemblyName> .  
  
 `ppIUnk`  
 in Ein Array vom Typ [IUnknown](/cpp/atl/iunknown) , in dem die Schnittstellen Zeiger abgelegt werden sollen `IMetadataAssemblyImport` .  
  
 `cMax`  
 vorgenommen Die maximale Anzahl von Schnittstellen Zeigern, die in platziert werden können `ppIUnk` .  
  
 `pcAssemblies`  
 vorgenommen Die Anzahl der zurückgegebenen Schnittstellen Zeiger. Das heißt, die Anzahl der Schnittstellen Zeiger, die tatsächlich in platziert werden `ppIUnk` .  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName`wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine Assemblys vorhanden.|  
  
## <a name="remarks"></a>Bemerkungen  
 Bei Angabe eines Assemblynamens findet die- `FindAssembliesByName` Methode die Assembly, indem Sie den Standardregeln zum Auflösen von Assemblyverweisen folgt. (Weitere Informationen finden Sie unter [so](../../deployment/how-the-runtime-locates-assemblies.md)sucht Common Language Runtime nach Assemblys.) ermöglicht dem Aufrufer, `FindAssembliesByName` verschiedene Aspekte des Assemblyresolverkontexts zu konfigurieren, z. b. Anwendungs Basis und privater Suchpfad.  
  
 Die- `FindAssembliesByName` Methode erfordert, dass die CLR im Prozess initialisiert wird, um die Assemblyauflösungs-Logik aufzurufen. Daher müssen Sie vor dem Aufrufen von [CoInitializeEE](../hosting/coinitializeee-function.md) (Übergabe COINITEE_DEFAULT) aufrufen `FindAssembliesByName` und dann mit einem Aufruf von " [zählinitializecor](../hosting/couninitializecor-function.md)" folgen.  
  
 `FindAssembliesByName`Gibt einen [IMetaDataImport](imetadataimport-interface.md) -Zeiger auf die Datei zurück, die das Assemblymanifest für den weiter gegebenen Assemblynamen enthält. Wenn der angegebene Assemblyname nicht vollständig angegeben ist (z. b. wenn er keine Version enthält), werden möglicherweise mehrere Assemblys zurückgegeben.  
  
 `FindAssembliesByName`wird häufig von einem Compiler verwendet, der versucht, eine referenzierte Assembly zur Kompilierzeit zu finden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [So sucht Common Language Runtime nach Assemblys](../../deployment/how-the-runtime-locates-assemblies.md)
- [IMetaDataAssemblyImport-Schnittstelle](imetadataassemblyimport-interface.md)
