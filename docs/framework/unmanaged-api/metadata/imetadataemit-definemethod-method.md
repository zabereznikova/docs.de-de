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
ms.openlocfilehash: d4f3c95428d6f0f8807e284c5b54582428176511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177668"
---
# <a name="imetadataemitdefinemethod-method"></a>IMetaDataEmit::DefineMethod-Methode
Erstellt eine Definition für eine Methode oder globale Funktion mit der angegebenen Signatur und gibt ein Token an diese Methodendefinition zurück.  
  
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
 [in] Das `mdTypedef` Token der übergeordneten Klasse oder übergeordneten Schnittstelle der Methode. Legen Sie fest, `td` dass , wenn Sie eine globale Funktion definieren. `mdTokenNil`  
  
 `szName`  
 [in] Der Membername in Unicode.  
  
 `dwMethodFlags`  
 [in] Ein Wert der [CorMethodAttr-Enumeration,](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) der die Attribute der Methode oder globalen Funktion angibt.  
  
 `pvSigBlob`  
 [in] Die Methodensignatur. Die Signatur wird wie angegeben beibehalten. Wenn Sie zusätzliche Informationen für Parameter angeben müssen, verwenden Sie die [IMetaDataEmit::SetParamProps-Methode.](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)  
  
 `cbSigBlob`  
 [in] Die Anzahl der `pvSigBlob`Bytes in .  
  
 `ulCodeRVA`  
 [in] Die Adresse des Codes.  
  
 `dwImplFlags`  
 [in] Ein Wert der [CorMethodImpl-Enumeration,](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) der die Implementierungsfeatures der Methode angibt.  
  
 `pmd`  
 [out] Das Membertoken.  
  
## <a name="remarks"></a>Bemerkungen  
 Die Metadaten-API garantiert, dass Methoden in der gleichen Reihenfolge beibehalten werden, in der der Aufrufer sie für eine bestimmte einschließende Klasse oder Schnittstelle ausgibt, die im `td` Parameter angegeben ist.  
  
 Weitere Informationen zur `DefineMethod` Verwendung und zu bestimmten Parametereinstellungen finden Sie unten.  
  
## <a name="slots-in-the-v-table"></a>Slots im V-Tisch  
 Die Laufzeit verwendet Methodendefinitionen, um v-Table-Slots einzurichten. In dem Fall, in dem ein oder mehrere Steckplätze übersprungen werden müssen, z. B. um die Parität mit einem COM-Schnittstellenlayout beizubehalten, wird eine Dummy-Methode definiert, um den Oder die Steckplätze in der v-Tabelle aufzunehmen. legen `dwMethodFlags` Sie `mdRTSpecialName` den Wert der [CorMethodAttr-Enumeration](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) fest, und geben Sie den Namen wie folgend:  
  
 _VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*>
  
 wobei *SequenceNumber* die Sequenznummer der Methode und *CountOfSlots* die Anzahl der Steckplätze ist, die in der v-Tabelle übersprungen werden sollen. Wenn *CountOfSlots* weggelassen wird, wird 1 angenommen. Diese Dummy-Methoden können weder aus verwaltetem noch aus nicht verwaltetem Code aufrufen, und jeder Versuch, sie aufzurufen, entweder aus verwaltetem oder nicht verwaltetem Code, generiert eine Ausnahme. Ihr einziger Zweck besteht darin, Platz in der v-Tabelle einzunehmen, die die Laufzeit für die COM-Integration generiert.  
  
## <a name="duplicate-methods"></a>Doppelte Methoden  
 Sie sollten keine doppelten Methoden definieren. Das heißt, Sie `DefineMethod` sollten nicht mit einem `td`doppelten `wzName`Satz `pvSig` von Werten in , und Parameteraufrufen aufrufen. (Diese drei Parameter zusammen definieren die Methode eindeutig.). Sie können jedoch ein doppeltes Triple verwenden, vorausgesetzt, dass Sie `mdPrivateScope` für `dwMethodFlags` eine der Methodendefinitionen das Bit im Parameter festlegen. (Das `mdPrivateScope` Bit bedeutet, dass der Compiler keinen Verweis auf diese Methodendefinition ausgibt.)  
  
## <a name="method-implementation-information"></a>Informationen zur Methodenimplementierung  
 Informationen über die Methodenimplementierung sind zum Zeitpunkt der Dekandieren der Methode oft nicht bekannt. Daher müssen Sie beim Aufrufen keine `ulCodeRVA` `dwImplFlags` Werte in `DefineMethod`der und Parameter übergeben. Die Werte können später über [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) oder [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), angegeben werden.  
  
 In einigen Situationen, z. B. Plattformaufruf (PInvoke) oder COM-Interop-Szenarien, wird der Methodentext nicht bereitgestellt und `ulCodeRVA` sollte auf Null gesetzt werden. In diesen Situationen sollte die Methode nicht als abstrakt markiert werden, da die Laufzeit die Implementierung findet.  
  
## <a name="defining-a-method-for-pinvoke"></a>Definieren einer Methode für PInvoke  
 Für jede nicht verwaltete Funktion, die über PInvoke aufgerufen werden soll, müssen Sie eine verwaltete Methode definieren, die die nicht verwaltete Zielfunktion darstellt. Um die verwaltete `DefineMethod` Methode zu definieren, verwenden Sie einige der Parameter, die auf bestimmte Werte festgelegt sind, abhängig von der Art und Weise, in der PInvoke verwendet wird:  
  
- True PInvoke - beinhaltet den Aufruf einer externen nicht verwalteten Methode, die sich in einer nicht verwalteten DLL befindet.  
  
- Lokaler PInvoke - umfasst den Aufruf einer systemeigenen nicht verwalteten Methode, die in das aktuelle verwaltete Modul eingebettet ist.  
  
 Die Parametereinstellungen sind in der folgenden Tabelle angegeben.  
  
|Parameter|Werte für true PInvoke|Werte für lokale PInvoke|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Set `mdStatic`; klar `mdSynchronized` `mdAbstract`und .|  
|`pvSigBlob`|Eine gültige CLR-Methodensignatur (Common Language Runtime) mit Parametern, die gültige verwaltete Typen sind.|Eine gültige CLR-Methodensignatur mit Parametern, die gültige verwaltete Typen sind.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Legen Sie `miCil` und `miManaged` fest.|Legen Sie `miNative` und `miUnmanaged` fest.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
