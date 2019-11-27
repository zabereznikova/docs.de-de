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
ms.openlocfilehash: c46b075341742aac605537a08b762b3cf47ef35b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431806"
---
# <a name="imetadataemitdefinemethod-method"></a>IMetaDataEmit::DefineMethod-Methode
Erstellt eine Definition für eine Methode oder eine globale Funktion mit der angegebenen Signatur und gibt ein Token an diese Methoden Definition zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
  
## <a name="parameters"></a>Parameter  
 `td`  
 in Das `mdTypedef` Token der übergeordneten Klasse oder übergeordneten Schnittstelle der Methode. Legen Sie `td` auf `mdTokenNil`fest, wenn Sie eine globale Funktion definieren.  
  
 `szName`  
 in Der Elementname in Unicode.  
  
 `dwMethodFlags`  
 in Ein Wert der [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) -Enumeration, der die Attribute der Methode oder globalen Funktion angibt.  
  
 `pvSigBlob`  
 in Die Methoden Signatur. Die Signatur wird wie angegeben beibehalten. Wenn Sie zusätzliche Informationen für Parameter angeben müssen, verwenden Sie die [IMetaDataEmit:: setparamrequismethode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) .  
  
 `cbSigBlob`  
 in Die Anzahl der Bytes in `pvSigBlob`.  
  
 `ulCodeRVA`  
 in Die Adresse des Codes.  
  
 `dwImplFlags`  
 in Ein Wert der [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) -Enumeration, der die Implementierungs Funktionen der Methode angibt.  
  
 `pmd`  
 vorgenommen Das Member-Token.  
  
## <a name="remarks"></a>Hinweise  
 Die metadatenapi garantiert, dass Methoden in derselben Reihenfolge beibehalten werden, in der der Aufrufer Sie für eine bestimmte einschließende Klasse oder Schnittstelle ausgibt, die im `td`-Parameter angegeben wird.  
  
 Weitere Informationen zur Verwendung von `DefineMethod` und bestimmten Parametereinstellungen finden Sie unten.  
  
## <a name="slots-in-the-v-table"></a>Slots in der V-Tabelle  
 Die Laufzeit verwendet Methoden Definitionen zum Einrichten von v-Table-Slots. Wenn ein oder mehrere Slots übersprungen werden müssen, z. b. um die Parität mit einem COM-Schnittstellen Layout beizubehalten, wird eine Pseudo Methode definiert, um den Slot oder die Einschub Fächer in der v-Tabelle zu nehmen. Legen Sie den `dwMethodFlags` auf den `mdRTSpecialName` Wert der [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) -Enumeration fest, und geben Sie den Namen wie folgt an:  
  
 _VtblGap\<*sequencenumschlag*> *\<\_>*
  
 Dabei ist " *sequencenenumber* " die Sequenznummer der Methode, und " *zählslots* " ist die Anzahl der Slots, die in der v-Tabelle ausgelassen werden. Wenn " *zählslots* " weggelassen wird, wird 1 angenommen. Diese Dummy-Methoden können nicht aus verwaltetem oder nicht verwaltetem Code aufgerufen werden, und jeder Versuch, Sie aus verwaltetem oder nicht verwaltetem Code aufzurufen, generiert eine Ausnahme. Der einzige Zweck besteht darin, in der v-Tabelle, die die Common Language Runtime für die com-Integration generiert, Speicherplatz zu belegen.  
  
## <a name="duplicate-methods"></a>Doppelte Methoden  
 Sie sollten keine doppelten Methoden definieren. Das heißt, Sie sollten `DefineMethod` nicht mit einem doppelten Satz von Werten in den Parametern `td`, `wzName`und `pvSig` aufzurufen. (Mit diesen drei Parametern wird die Methode eindeutig definiert.) Sie können jedoch ein doppeltes Triple verwenden, vorausgesetzt, dass Sie für eine der Methoden Definitionen das `mdPrivateScope` Bit im `dwMethodFlags`-Parameter festlegen. (Das `mdPrivateScope` Bit bedeutet, dass der Compiler keinen Verweis auf diese Methoden Definition ausgibt.)  
  
## <a name="method-implementation-information"></a>Methoden Implementierungs Informationen  
 Informationen zur Methoden Implementierung sind häufig nicht bekannt, wenn die-Methode deklariert wird. Daher müssen Sie beim Aufrufen von `DefineMethod`keine Werte in den `ulCodeRVA`-und `dwImplFlags`-Parametern übergeben. Die Werte können später über [IMetaDataEmit:: SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) oder [IMetaDataEmit:: SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)bereitgestellt werden.  
  
 In einigen Situationen, z. b. PInvoke-oder COM-Interop-Szenarien, wird der Methoden Text nicht bereitgestellt, und `ulCodeRVA` sollte auf 0 (null) festgelegt werden. In diesen Fällen sollte die-Methode nicht als abstrakt gekennzeichnet werden, da die-Laufzeit die-Implementierung findet.  
  
## <a name="defining-a-method-for-pinvoke"></a>Definieren einer Methode für PInvoke  
 Für jede nicht verwaltete Funktion, die über PInvoke aufgerufen werden soll, müssen Sie eine verwaltete Methode definieren, die die nicht verwaltete Zielfunktion darstellt. Um die verwaltete Methode zu definieren, verwenden Sie `DefineMethod` mit einigen Parametern, die auf bestimmte Werte festgelegt sind, abhängig von der Art und Weise, wie PInvoke verwendet wird:  
  
- True PInvoke: umfasst den Aufruf einer externen nicht verwalteten Methode, die sich in einer nicht verwalteten DLL befindet.  
  
- Local PInvoke: umfasst den Aufruf einer nativen, nicht verwalteten Methode, die in das aktuelle verwaltete Modul eingebettet ist.  
  
 Die Parametereinstellungen sind in der folgenden Tabelle angegeben.  
  
|Parameter|Werte für true PInvoke|Werte für local PInvoke|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||`mdStatic`festlegen; Löschen Sie `mdSynchronized` und `mdAbstract`.|  
|`pvSigBlob`|Eine gültige common Language Runtime (CLR)-Methoden Signatur mit Parametern, die gültige verwaltete Typen sind.|Eine gültige CLR-Methoden Signatur mit Parametern, die gültige verwaltete Typen sind.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Legen Sie `miCil` und `miManaged`fest.|Legen Sie `miNative` und `miUnmanaged`fest.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
