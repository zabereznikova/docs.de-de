---
title: IMetaDataEmit::DefineMethod-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2dbc6b5ffaa3a381bdd657059a682a3d12dc4cf1
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46584265"
---
# <a name="imetadataemitdefinemethod-method"></a>IMetaDataEmit::DefineMethod-Methode
Erstellt eine Definition für eine Methode oder globalen Funktion mit der angegebenen Signatur und ein Token an dieser Methodendefinition zurück.  
  
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
 [in] Die `mdTypedef` token von der übergeordneten Klasse oder Schnittstelle der Methode. Legen Sie `td` zu `mdTokenNil`, wenn Sie eine globale Funktion definieren.  
  
 `szName`  
 [in] Der Elementname im Unicode-Format.  
  
 `dwMethodFlags`  
 [in] Der Wert der [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) -Enumeration, die die Attribute der Methode oder globalen Funktion angibt.  
  
 `pvSigBlob`  
 [in] Die Signatur der Methode. Die Signatur wird beibehalten, wie angegeben. Wenn Sie zusätzliche Informationen für alle Parameter angeben müssen, verwenden Sie die [IMetaDataEmit:: SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) Methode.  
  
 `cbSigBlob`  
 [in] Die Anzahl der Bytes im `pvSigBlob`.  
  
 `ulCodeRVA`  
 [in] Die Adresse des Codes.  
  
 `dwImplFlags`  
 [in] Der Wert der [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) -Enumeration, die die Implementierung der Methode angibt.  
  
 `pmd`  
 [out] Das Membertoken.  
  
## <a name="remarks"></a>Hinweise  
 Die Metadaten-API-Methoden in der gleichen Reihenfolge beibehalten werden, wie der Aufrufer sie für eine bestimmte einschließende Klasse oder Schnittstelle, die im angegebenen ausgibt garantiert die `td` Parameter.  
  
 Weitere Informationen zur Verwendung von `DefineMethod` und bestimmte Einstellungen sind unten angegeben.  
  
## <a name="slots-in-the-v-table"></a>Slots in die V-Tabelle  
 Die Runtime verwendet die Methodendefinitionen zum Einrichten von vtable-Slots. Im Fall, in denen eine oder mehrere Slots übersprungen werden, z. B. müssen, ist, die Parität mit einem Layout mit einem COM-Schnittstelle beibehalten eine dummy Methode definiert, um beanspruchen, bis das oder die Slots in der vtable; Festlegen der `dwMethodFlags` auf die `mdRTSpecialName` Wert der [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) Enumeration und geben Sie den Namen als:  
  
 _VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*>
  
 wo *SequenceNumber* ist die Sequenznummer der Methode und *CountOfSlots* ist die Anzahl der Slots in der vtable-übersprungen werden sollen. Wenn *CountOfSlots* wird weggelassen, wird bei 1 begonnen. Diese dummy-Methoden sind nicht von verwalteten oder nicht verwalteten Code, und jeder Versuch, die sie von verwalteten oder nicht verwalteten Code aufrufen, wird eine Ausnahme generiert. Ihr einziger Zweck ist, in der vtable-Platz einnehmen, die die Laufzeit für die Integration von COM-generiert.  
  
## <a name="duplicate-methods"></a>Doppelte Methoden  
 Sie sollten keine doppelte Methoden definieren. Das heißt, Sie sollten nicht aufrufen, `DefineMethod` mit einen doppelten Satz von Werten in der `td`, `wzName`, und `pvSig` Parameter. (Diese drei Parameter zusammen eindeutig definieren Sie die Methode.). Allerdings können Sie ein doppeltes Tripel verwenden, vorausgesetzt, dass für eine der Methodendefinitionen, Sie legen die `mdPrivateScope` bit in der `dwMethodFlags` Parameter. (Die `mdPrivateScope` -Bit bedeutet, dass der Compiler einen Verweis auf die Methodendefinition nicht ausgeben werden.)  
  
## <a name="method-implementation-information"></a>Implementierung von Informationen  
 Informationen über die Implementierung der Methode wird zur Zeit, die die Methode deklariert wird, oft nicht bekannt. Aus diesem Grund, Sie müssen nicht übergeben von Werten in der `ulCodeRVA` und `dwImplFlags` Parameter beim Aufrufen von `DefineMethod`. Die Werte können später über angegeben werden [IMetaDataEmit:: SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) oder [SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)je nach Bedarf.  
  
 In einigen Situationen, z. B. Plattformaufrufe (PInvoke) oder COM-Interop-Szenarien, Hauptteil der Methode wird nicht bereitgestellt werden, und `ulCodeRVA` auf 0 (null) festgelegt werden. In diesen Situationen sollte die Methode nicht als abstrakt markiert werden, da die Laufzeit wird die Implementierung nicht finden.  
  
## <a name="defining-a-method-for-pinvoke"></a>Definieren eine Methode für PInvoke  
 Für jede nicht verwaltete Funktion, die über PInvoke aufgerufen werden müssen Sie eine verwaltete Methode definieren, die die, die nicht verwaltete Zielfunktion darstellt. Verwenden Sie zum Definieren der verwalteten Methode `DefineMethod` mit den Parametern, die bestimmten Werten, je nachdem, wie in der PInvoke verwendet wird:  
  
-   "True" PInvoke - schließt den Aufruf einer externen nicht verwaltete Methode, die in einer nicht verwalteten DLL befinden.  
  
-   Lokale PInvoke - schließt den Aufruf einer systemeigenen, nicht verwaltete Methode, die im aktuellen verwalteten Modul eingebettet ist.  
  
 Die parametereinstellungen, werden in der folgenden Tabelle angegeben.  
  
|Parameter|Werte für "true" PInvoke|Werte für lokale PInvoke|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Legen Sie `mdStatic`; löschen `mdSynchronized` und `mdAbstract`.|  
|`pvSigBlob`|Gültige common Language Runtime (CLR) Signatur einer Methode mit Parametern, die gültig sind von verwalteten Typen.|Eine gültige CLR-Methodensignatur mit Parametern, die gültig sind von verwalteten Typen.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Legen Sie `miCil` und `miManaged`.|Legen Sie `miNative` und `miUnmanaged`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
