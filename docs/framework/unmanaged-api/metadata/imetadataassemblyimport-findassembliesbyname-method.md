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
ms.openlocfilehash: c0f81e3767d4ea3bc336203fbe8c914b4e2bd07b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177798"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>IMetaDataAssemblyImport::FindAssembliesByName-Methode
Ruft ein Array von `szAssemblyName` Assemblys mit dem angegebenen Parameter ab, wobei die Standardregeln verwendet werden, die von der Common Language Runtime (CLR) zum Auflösen von Verweisen verwendet werden.  
  
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
 [in] Das Stammverzeichnis, in dem nach der angegebenen Assembly gesucht werden soll. Wenn dieser Wert `null`auf `FindAssembliesByName` festgelegt ist, wird nur im globalen Assemblycache für die Assembly gesucht.  
  
 `szPrivateBin`  
 [in] Eine Liste von Subverzeichnissen, die durch Semikolons getrennt sind (z. B. "bin;bin2"), unter dem Stammverzeichnis, in dem nach der Assembly gesucht werden soll. Diese Verzeichnisse werden zusätzlich zu den in den Standardprüfregeln angegebenen Prüfregeln untersucht.  
  
 `szAssemblyName`  
 [in] Der Name der zu suchenden Assembly. Das Format dieser Zeichenfolge ist in der <xref:System.Reflection.AssemblyName>Klassenreferenzseite für definiert.  
  
 `ppIUnk`  
 [in] Ein Array vom Typ [IUnknown,](/cpp/atl/iunknown) in dem die `IMetadataAssemblyImport` Schnittstellenzeiger gesetzt werden sollen.  
  
 `cMax`  
 [out] Die maximale Anzahl von Schnittstellenzeigern, `ppIUnk`die in platziert werden können.  
  
 `pcAssemblies`  
 [out] Die Anzahl der zurückgegebenen Schnittstellenzeiger. Das heißt, die Anzahl der Schnittstellenzeiger, die tatsächlich in `ppIUnk`platziert wurden.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName`erfolgreich zurückgegeben werden.|  
|`S_FALSE`|Es sind keine Assemblys vorhanden.|  
  
## <a name="remarks"></a>Bemerkungen  
 Bei einem Assemblynamen `FindAssembliesByName` findet die Methode die Assembly, indem sie den Standardregeln zum Auflösen von Assemblyverweisen folgt. (Weitere Informationen finden Sie unter [So findet die Laufzeit Assemblys](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` ermöglicht es dem Aufrufer, verschiedene Aspekte des Assembly-Resolver-Kontexts zu konfigurieren, z. B. Anwendungsbasis und privater Suchpfad.  
  
 Die `FindAssembliesByName` Methode erfordert, dass die CLR im Prozess initialisiert wird, um die Assemblyauflösungslogik aufzurufen. Daher müssen Sie [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (übergeben COINITEE_DEFAULT) aufrufen, bevor Sie aufrufen, `FindAssembliesByName`und dann mit einem Aufruf von [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)folgen.  
  
 `FindAssembliesByName`gibt einen [IMetaDataImport-Zeiger](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) auf die Datei zurück, die das Assemblymanifest für den übergebenen Assemblynamen enthält. Wenn der angegebene Assemblyname nicht vollständig angegeben ist (z. B. wenn er keine Version enthält), können mehrere Assemblys zurückgegeben werden.  
  
 `FindAssembliesByName`wird häufig von einem Compiler verwendet, der versucht, eine Assembly zu finden, auf die zur Kompilierungszeit verwiesen wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [So sucht die Laufzeit Assemblys](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
