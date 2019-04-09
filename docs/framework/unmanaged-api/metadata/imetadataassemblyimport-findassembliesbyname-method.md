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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b388dae0f109ff366f83c92de99b00b80bcc01a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108718"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>IMetaDataAssemblyImport::FindAssembliesByName-Methode
Ruft ein Array von Assemblys mit dem angegebenen `szAssemblyName` Parameters unter Verwendung von die Standardregeln, die von der common Language Runtime (CLR) zum Auflösen von verweisen.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [in] Das Stammverzeichnis, in denen für die angegebene Assembly gesucht werden soll. Wenn dieser Wert, um festgelegt ist `null`, `FindAssembliesByName` wird nur im globalen Assemblycache suchen Sie nach der Assembly.  
  
 `szPrivateBin`  
 [in] Eine Liste von durch Semikolons getrennte Unterverzeichnisse (z. B. "Bin; bin2"), unter dem Stammverzeichnis, in dem für die Assembly gesucht werden soll. Diese Verzeichnisse sind zusätzlich zu den in der Überprüfung der Regeln angegeben sind.  
  
 `szAssemblyName`  
 [in] Der Name der Assembly zu suchen. Das Format dieser Zeichenfolge wird definiert, in der Klasse Referenzseite für <xref:System.Reflection.AssemblyName>.  
  
 `ppIUnk`  
 [in] Ein Array vom Typ [IUnknown](/cpp/atl/iunknown) zum Speichern der `IMetadataAssemblyImport` Schnittstellenzeigern.  
  
 `cMax`  
 [out] Die maximale Anzahl der Schnittstellenzeiger, der in eingefügt werden können `ppIUnk`.  
  
 `pcAssemblies`  
 [out] Die Anzahl der Schnittstellenzeiger zurückgegeben. D. h. die Anzahl der Schnittstellenzeiger, die tatsächlich `ppIUnk`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine Assemblys.|  
  
## <a name="remarks"></a>Hinweise  
 Erhält den Namen einer Assembly die `FindAssembliesByName` Methode sucht die Assembly, indem Sie die folgenden Standardregeln für das Auflösen von Assemblyverweisen. (Weitere Informationen finden Sie unter [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` ermöglicht dem Aufrufer, die verschiedene Aspekte der Kontext des Assembly-Auflösung, z. B. Basisklassen und privaten Suchpfad konfigurieren.  
  
 Die `FindAssembliesByName` Methode muss die CLR im Prozess initialisiert werden, um die Logik zur Assembly aufzurufen. Aus diesem Grund müssen Sie aufrufen [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (COINITEE_DEFAULT übergeben) vor dem Aufruf `FindAssembliesByName`, und befolgen Sie dann mit einem Aufruf von [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName` Gibt eine [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Zeiger auf die Datei mit dem Assemblymanifest für die Namen der Assembly, die übergeben wird. Wenn der angegebene Assemblyname (z. B., wenn eine Version nicht enthalten ist) nicht vollständig angegeben wurde, können mehrere Assemblys zurückgegeben werden.  
  
 `FindAssembliesByName` wird häufig durch einen Compiler verwendet, die versucht, eine referenzierte Assembly zum Zeitpunkt der Kompilierung zu finden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [So sucht Common Language Runtime nach Assemblys](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
