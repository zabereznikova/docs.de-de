---
title: IMetaDataEmit::DefineMethod-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMethod
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: de55ee714dcba512befae3d2311a9880a08ba29f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinemethod-method"></a>IMetaDataEmit::DefineMethod-Methode
Erstellt eine Definition für eine Methode oder globalen Funktion mit der angegebenen Signatur und gibt ein Token für diese Methodendefinition zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DefineMethod (      
    [in]  mdTypeDef         td,   
    [in]  LPCWSTR           szName,   
    [in]  DWORD             dwMethodFlags,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [in]  ULONG             ulCodeRVA,   
    [in]  DWORD             dwImplFlags,   
    [out] mdMethodDef      *pmd  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `td`  
 [in] Die `mdTypedef` der übergeordneten Klasse oder übergeordneten Schnittstelle der Methode. Legen Sie `td` zu `mdTokenNil`, wenn Sie eine globale Funktion definieren.  
  
 `szName`  
 [in] Der Elementname im Unicode-Format.  
  
 `dwMethodFlags`  
 [in] Der Wert der [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) -Enumeration, die die Attribute der Methode oder globalen Funktion angibt.  
  
 `pvSigBlob`  
 [in] Die Methodensignatur. Die Signatur wird beibehalten, wie angegeben. Wenn Sie zusätzliche Informationen für alle Parameter angeben müssen, verwenden Sie die [IMetaDataEmit:: SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) Methode.  
  
 `cbSigBlob`  
 [in] Die Anzahl der Bytes im `pvSigBlob`.  
  
 `ulCodeRVA`  
 [in] Die Adresse des Codes.  
  
 `dwImplFlags`  
 [in] Der Wert der [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) -Enumeration, die Features zur Implementierung der Methode angibt.  
  
 `pmd`  
 [out] Das Membertoken.  
  
## <a name="remarks"></a>Hinweise  
 Die Metadaten-API-Methoden in der gleichen Reihenfolge beizubehalten, wie der Aufrufer sie für eine bestimmte einschließende Klasse oder Schnittstelle, die im angegebenen ausgibt garantiert, dass die `td` Parameter.  
  
 Weitere Informationen zur Verwendung von `DefineMethod` und bestimmten parametereinstellungen unten angegebenen ist.  
  
## <a name="slots-in-the-v-table"></a>Slots in der V-Tabelle  
 Die Laufzeit verwendet Methodendefinitionen Funktionstabelle Slots einrichten. Im Fall, in denen eine oder mehrere Slots übersprungen werden, z. B. müssen, hinsichtlich Parität mit einem COM-Schnittstellenlayout beibehalten eine dummy-Methode definiert, um den oder die Slots in der Funktionstabelle auszufüllen klicken. Festlegen der `dwMethodFlags` auf die `mdRTSpecialName` Wert der [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) Enumeration und geben Sie den Namen als:  
  
 _VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*>  
  
 wobei *SequenceNumber* ist die Sequenznummer der Methode und *CountOfSlots* ist die Anzahl der Slots in der Funktionstabelle übersprungen werden sollen. Wenn *CountOfSlots* wird weggelassen, wird 1 ausgegangen. Dieser dummy-Methoden sind nicht aus verwaltetem oder nicht verwaltetem Code aufgerufen werden kann, und jeder Versuch, aus verwaltetem oder nicht verwalteten Code aufrufen, wird eine Ausnahme generiert. Ihre einzige dient in vtable-Platz einnehmen, die die Laufzeit für die COM-Integration generiert.  
  
## <a name="duplicate-methods"></a>Doppelte Methoden  
 Sie sollten keine doppelten Methoden definieren. D. h., Sie sollten nicht aufrufen `DefineMethod` mit einem doppelten Satz von Werten in der `td`, `wzName`, und `pvSig` Parameter. (Diese drei Parameter zusammen definieren Sie die Methode eindeutig.). Sie können jedoch ein doppeltes Tripel verwenden, vorausgesetzt, dass für eine der Methodendefinitionen, Sie legen die `mdPrivateScope` bit in der `dwMethodFlags` Parameter. (Die `mdPrivateScope` Bit bedeutet, dass der Compiler einen Verweis auf die Methodendefinition ausgegeben wird.)  
  
## <a name="method-implementation-information"></a>Informationen zur Implementierung  
 Informationen über die Implementierung der Methode wird häufig nicht zu dem Zeitpunkt bezeichnet, in der die Methode deklariert wird. Aus diesem Grund, Sie müssen nicht übergeben von Werten in der `ulCodeRVA` und `dwImplFlags` Parameter beim Aufrufen von `DefineMethod`. Die Werte können später durch angegeben [IMetaDataEmit:: SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) oder [SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)je nach Bedarf.  
  
 In einigen Situationen, z. B. Platform-Aufruf (PInvoke) oder COM-Interop-Szenarios, Methodentext wird nicht bereitgestellt werden, und `ulCodeRVA` sollte auf 0 (null) festgelegt werden. In diesen Situationen sollte die Methode nicht als abstrakt markiert werden, da die Laufzeit die Implementierung suchen.  
  
## <a name="defining-a-method-for-pinvoke"></a>Definieren eine Methode für PInvoke  
 Für jede nicht verwaltete Funktion, die über PInvoke aufgerufen wird müssen Sie eine verwaltete Methode definieren, die das, die nicht verwaltete Zielfunktion darstellt. Verwenden Sie zum Definieren der verwalteten Methode `DefineMethod` mit einigen der Parameter auf bestimmte Werte abhängig von der Anzeigemethode in der PInvoke verwendet wird:  
  
-   "True" PInvoke - schließt den Aufruf einer externen nicht verwaltete Methode, die in einer nicht verwalteten DLL befindet.  
  
-   Lokale PInvoke - schließt den Aufruf einer systemeigenen, nicht verwaltete Methode, die in der aktuellen verwalteten Modul eingebettet ist.  
  
 Die parametereinstellungen, werden in der folgenden Tabelle angegeben.  
  
|Parameter|Werte für "true" PInvoke|Werte für lokale PInvoke|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Legen Sie `mdStatic`; clear `mdSynchronized` und `mdAbstract`.|  
|`pvSigBlob`|Gültige common Language Runtime (CLR) Signatur einer Methode mit Parametern, die gültig sind von verwalteten Typen.|Eine gültige CLR-Methodensignatur mit Parametern, die gültig sind von verwalteten Typen.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Legen Sie `miCil` und `miManaged`.|Legen Sie `miNative` und `miUnmanaged`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
