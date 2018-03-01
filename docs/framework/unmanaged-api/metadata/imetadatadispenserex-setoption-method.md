---
title: IMetaDataDispenserEx::SetOption-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataDispenserEx.SetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::SetOption
helpviewer_keywords:
- IMetaDataDispenserEx::SetOption method [.NET Framework metadata]
- SetOption method [.NET Framework metadata]
ms.assetid: 9f1c7ccd-7fb2-41d8-aa00-24b823376527
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 96810ba0eab99d1df58f0b68b85ef4da8ce7084e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserexsetoption-method"></a>IMetaDataDispenserEx::SetOption-Methode
Legt die angegebene Option auf einen angegebenen Wert für den aktuellen Metadatenbereich fest. Die Option wird gesteuert, wie Aufrufe im aktuellen Metadatenbereich behandelt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetOption (  
    [in] REFGUID optionId,   
    [in] const VARIANT *pValue  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `optionId`  
 [in] Ein Zeiger auf eine GUID fest, der angibt, die Option festgelegt werden.  
  
 `pValue`  
 [in] Der Wert für die Option festgelegt. Der Typ dieses Werts muss eine Variante des Typs für die angegebene Option.  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Tabelle listet die verfügbaren GUIDs, die die `optionId` auf Parameter verweisen und die entsprechende gültige Werte für die `pValue` Parameter.  
  
|GUID|Beschreibung|`pValue`Parameter|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|Steuert, welche Elemente auf Duplikate überprüft werden. Bei jedem Aufruf ein [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) Methode, die ein neues Element erstellt, bitten Sie die Methode überprüft, ob das Element im aktuellen Gültigkeitsbereich bereits vorhanden ist. Sie können beispielsweise überprüfen, das Vorhandensein des `mdMethodDef` Elemente; in diesem Fall beim Aufruf [IMetaDataEmit:: DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), überprüft die Methode im aktuellen Bereich nicht bereits vorhanden ist. Diese Überprüfung verwendet den Schlüssel, der eine bestimmte Methode eindeutig identifiziert: übergeordneter Typ, Name und Signatur.|Muss eine Variante des Typs UI4 sein und darf eine Kombination der Werte für die [CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) Enumeration.|  
|MetaDataRefToDefCheck|Steuert, die welche Elemente auf die verwiesen wird, werden in Definitionen konvertiert. Standardmäßig wird das Metadatenmodul den Code optimieren, indem Sie ein Element verwiesen wird, der Definition konvertieren, wenn das Element verwiesen wird, tatsächlich im aktuellen Bereich definiert ist.|Muss eine Variante des Typs UI4 sein und darf eine Kombination der Werte für die [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) Enumeration.|  
|MetaDataNotificationForTokenMovement|Steuerelemente, die die Token ordnet auftritt, während ein Zusammenführen von Metadaten Rückrufe zu generieren. Verwenden der [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) Methode zum Herstellen der [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) Schnittstelle.|Muss eine Variante des Typs UI4 sein und darf eine Kombination der Werte für die [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) Enumeration.|  
|MetaDataSetENC|Steuert das Verhalten von bearbeiten und Fortfahren (ENC). Nur einen Modus Verhalten kann zu einem Zeitpunkt festgelegt werden.|Muss eine Variante des Typs UI4 sein und darf der Wert der [CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) Enumeration. Der Wert ist eine Bitmaske.|  
|MetaDataErrorIfEmitOutOfOrder|Steuert, welche Fehler ausgegeben,-außerhalb der normalen Reihenfolge Rückrufe zu generieren. Ausgeben von Metadaten, die außerhalb der Reihenfolge ist nicht schwerwiegend. Wenn Sie Metadaten in eine Bestellung, die vom Metadatenmodul bevorzugt wird auszugeben, die Metadaten ist jedoch kompakter und kann daher effizienter durchsucht werden. Verwenden der `IMetaDataEmit::SetHandler` Methode zum Herstellen der [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) Schnittstelle.|Muss eine Variante des Typs UI4 sein und darf eine Kombination der Werte für die [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) Enumeration.|  
|MetaDataImportOption|Steuert, welche Arten von Elementen, die während eines ENC gelöscht wurden, die durch ein Enumerator abgerufen werden.|Muss eine Variante des Typs UI4 sein und darf eine Kombination der Werte für die [CorImportOptions-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) Enumeration.|  
|MetaDataThreadSafetyOptions|Steuert, ob das Metadatenmodul Leser/Schreibersperre sperren, gewährleisteten Threadsicherheit erhält. Standardmäßig nimmt das Modul an, dass der Zugriff durch den Aufrufer Singlethread ist, sodass keine Sperren abgerufen werden. Clients sind zuständig für die Verwaltung von richtigen Threadsynchronisierung, wenn die Metadaten-API verwendet.|Muss eine Variante des Typs UI4 sein und darf der Wert der [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) Enumeration. Der Wert ist eine Bitmaske.|  
|MetaDataGenerateTCEAdapters|Steuert, ob das Type Library Importer-Tool die eng verkoppelten Ereignis (TCE)-Adapter für COM-Connection Point Container generiert werden sollen.|Muss eine Variante vom Typ bool fest. Wenn `pValue` festgelegt ist, um `true`, Type Library Importer-Tool generiert die TCE-Adapter.|  
|MetaDataTypeLibImportNamespace|Gibt einen nicht standardmäßigen Namespace für die Typbibliothek, die importiert wird.|Hierbei muss es sich um einen null-Wert oder eine Variante des BSTR-Typ sein. Wenn `pValue` ist ein null-Wert, der aktuelle Namespace ist auf null festgelegt; andernfalls, der aktuelle Namespace festgelegt ist, auf die Zeichenfolge, die in der Variante BSTR-Typ gespeichert ist.|  
|MetaDataLinkerOptions|Steuert, ob der Linker eine Assembly oder eine .NET Framework-Modul-Datei generieren soll.|Muss eine Variante des Typs UI4 sein und darf eine Kombination der Werte für die [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) Enumeration.|  
|MetaDataRuntimeVersion|Gibt die Version der common Language Runtime für die dieses Image erstellt wurde. Die Version wird als eine Zeichenfolge, z. B. "Version"1.0.3705 gespeichert.|Hierbei muss es sich um einen null-Wert, ein VT_EMPTY-Wert oder eine Variante des BSTR-Typ sein. Wenn `pValue` ist null, wird die Laufzeitversion festgelegt auf Null. Wenn `pValue` VT_EMPTY, ist die Version wird festgelegt, um einen Standardwert, der von der Version von Mscorwks.dll gezogen wird, anhand derer die Metadatencode ausgeführt wird. Andernfalls wird die Laufzeitversion auf die Zeichenfolge festgelegt, die in der Variante BSTR-Typ gespeichert ist.|  
|MetaDataMergerOptions|Gibt Optionen für das Zusammenführen von Metadaten.|Muss eine Variante des Typs UI4 sein und darf eine Kombination der Werte für die `MergeFlags` -Enumeration, die in der Datei "CorHdr.h" beschrieben wird.|  
|MetaDataPreserveLocalRefs|Deaktiviert Optimierung von lokalen Verweisen in Definitionen.|Muss enthalten eine Kombination der Werte für die [CorLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) Enumeration.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
