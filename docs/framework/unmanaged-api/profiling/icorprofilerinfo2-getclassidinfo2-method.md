---
title: ICorProfilerInfo2::GetClassIDInfo2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
ms.openlocfilehash: 64d2cd76dafb1a51814b916b5ce73fb08cdcaef9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868859"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a>ICorProfilerInfo2::GetClassIDInfo2-Methode
Ruft das übergeordnete Modul und das Metadatentoken für die offene generische Definition der angegebenen Klasse, den `ClassID` der übergeordneten Klasse und die `ClassID` für jedes Typargument (sofern vorhanden) der Klasse ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a>Parameters  
 `classId`  
 [in] Die ID der Klasse, für die Informationen abgerufen werden sollen.  
  
 `pModuleId`  
 vorgenommen Ein Zeiger auf die ID des übergeordneten Moduls für die offene generische Definition der angegebenen Klasse.  
  
 `pTypeDefToken`  
 vorgenommen Zeiger auf das Metadatentoken für die offene generische Definition der angegebenen Klasse.  
  
 `pParentClassId`  
 [out] Der Zeiger auf die ID der übergeordneten Klasse.  
  
 `cNumTypeArgs`  
 [in] Die Größe des `typeArgs`-Arrays.  
  
 `pcNumTypeArgs`  
 [out] Der Zeiger auf die Gesamtzahl der verfügbaren Elemente.  
  
 `typeArgs`  
 [out] Ein Array von `ClassID`-Werten, von denen jedes die ID eines Typarguments der Klasse darstellt. Wenn die Methode zurückkehrt, enthält `typeArgs` einige verfügbare oder alle verfügbaren `ClassID` Werte.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetClassIDInfo2`-Methode ähnelt der [ICorProfilerInfo:: GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md) -Methode, `GetClassIDInfo2` erhält jedoch zusätzliche Informationen über einen generischen Typ.  
  
 Der Profiler-Code kann [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) aufrufen, um eine [Metadatenschnittstelle](../../../../docs/framework/unmanaged-api/metadata/index.md) für ein bestimmtes Modul zu erhalten. Das Metadatentoken, das an den Speicherort zurückgegeben wird, auf den durch `pTypeDefToken` verwiesen wird, kann anschließend für den Zugriff auf die Metadaten für die Klasse verwendet werden.  
  
 Nachdem `GetClassIDInfo2` zurückgegeben wurde, müssen Sie sicherstellen, dass der `typeArgs`-Puffer groß genug war, um alle `ClassID`-Werte aufzunehmen. Vergleichen Sie zu diesem Zweck den Wert, auf den `pcNumTypeArgs` verweist, mit dem Wert des Parameters `cNumTypeArgs`. Wenn `pcNumTypeArgs` auf einen Wert verweist, der größer als `cNumTypeArgs` ist, weisen Sie einen größeren `typeArgs`-Puffer zu, aktualisieren Sie `cNumTypeArgs` mit der neuen Größe, und rufen Sie `GetClassIDInfo2` erneut auf.  
  
 Alternativ können Sie zuerst `GetClassIDInfo2` mit einem `typeArgs`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln. Sie können die `typeArgs`Puffergröße dann auf den Wert festlegen, der von `pcNumTypeArgs` zurückgegeben wurde, und `GetClassIDInfo2` dann erneut aufrufen.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
