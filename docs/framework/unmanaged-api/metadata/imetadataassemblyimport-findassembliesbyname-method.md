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
ms.openlocfilehash: a6c7bf332d829a440fe216756f7a23ec1277e6c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449285"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>IMetaDataAssemblyImport::FindAssembliesByName-Methode
Ruft ein Array von Assemblys mit dem angegebenen `szAssemblyName` Parameters unter Verwendung von Standardregeln, die von der common Language Runtime (CLR) zum Auflösen von verweisen.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `szAppBase`  
 [in] Das Stammverzeichnis, in denen für die angegebene Assembly gesucht werden soll. Wenn dieser Wert, um festgelegt wird `null`, `FindAssembliesByName` sieht nur im globalen Assemblycache nach der Assembly.  
  
 `szPrivateBin`  
 [in] Eine Liste von durch Semikolons getrennte Unterverzeichnissen (z. B. "Bin; bin2"), unter dem Stammverzeichnis, in dem für die Assembly gesucht werden soll. Diese Verzeichnisse werden zusätzlich zu den in der standardmäßigen Testregeln angegeben überprüft.  
  
 `szAssemblyName`  
 [in] Der Name der Assembly zu suchen. Das Format dieser Zeichenfolge wird in der Klasse Referenzseite für definiert <xref:System.Reflection.AssemblyName>.  
  
 `ppIUnk`  
 [in] Ein Array vom Typ <<!--zzxref:IUnknown --> `IUnknown`> zum Speichern der `IMetadataAssemblyImport` -Schnittstellenzeigern.  
  
 `cMax`  
 [out] Die maximale Anzahl von Schnittstellenzeigern, die in platziert werden können `ppIUnk`.  
  
 `pcAssemblies`  
 [out] Die Anzahl der zurückgegebenen Schnittstellenzeiger. D. h. die Anzahl der Schnittstellenzeiger, die tatsächlich `ppIUnk`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName` wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es gibt keine Assemblys.|  
  
## <a name="remarks"></a>Hinweise  
 Erhält den Namen einer Assembly der `FindAssembliesByName` Methode sucht nach der Assembly gemäß die Standardregeln für das Auflösen von Assemblyverweisen. (Weitere Informationen finden Sie unter [so sucht Common Language Runtime nach Assemblys](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` ermöglicht dem Aufrufer, die verschiedene Aspekte des Kontexts Konfliktlöser Assembly z. B. die Anwendungsbasis und privater Suchpfad konfigurieren.  
  
 Die `FindAssembliesByName` Methode muss die CLR im Prozess initialisiert werden, um die Assemblyauflösungslogik aufzurufen. Aus diesem Grund müssen Sie aufrufen [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (COINITEE_DEFAULT übergeben) vor dem Aufruf `FindAssembliesByName`, und befolgen Sie dann mit einem Aufruf von [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName` Gibt eine [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Zeiger auf die Datei, die das Manifest der Name der Assembly enthält, die übergeben wird. Der Name der angegebenen Assembly (z. B., wenn eine Version nicht enthalten ist) nicht vollständig angegeben ist, können mehrere Assemblys zurückgegeben werden.  
  
 `FindAssembliesByName` wird häufig von einem Compiler verwendet, die versucht, eine Assembly verwiesen wird, zum Zeitpunkt der Kompilierung gefunden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [So sucht Common Language Runtime nach Assemblys](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
