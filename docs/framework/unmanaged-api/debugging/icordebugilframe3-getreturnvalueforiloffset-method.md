---
title: ICorDebugILFrame3::GetReturnValueForILOffset-Methode
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
ms.openlocfilehash: 0d1ef6c1369fd399f5b36b24a21c4b5d7f1e80fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178816"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>ICorDebugILFrame3::GetReturnValueForILOffset-Methode
Ruft ein "ICorDebugValue"-Objekt ab, das den Rückgabewert einer Funktion kapselt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ILOffset`  
 Der IL-Offset. Weitere Informationen finden Sie im Abschnitt mit den Hinweisen.  
  
 `ppReturnValue`  
 Ein Zeiger auf die Adresse eines "ICorDebugValue"-Schnittstellenobjekts, das Informationen über den Rückgabewert eines Funktionsaufrufs bereitstellt.  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Methode wird zusammen mit der [ICorDebugCode3::GetReturnValueLiveOffset-Methode](icordebugcode3-getreturnvalueliveoffset-method.md) verwendet, um den Rückgabewert einer Methode abzubekommen. Dies ist für Methoden sehr nützlich, deren Rückgabewerte ignoriert wurden, wie in den folgenden beiden Codebeispielen dargestellt. Im ersten Beispiel wird die <xref:System.Int32.TryParse%2A?displayProperty=nameWithType>-Methode aufgerufen, der Rückgabewert der Methode jedoch ignoriert.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 Das zweite Beispiel veranschaulicht ein allgemeineres Problem beim Debuggen. Da eine Methode als Argument eines Methodenaufrufs verwendet wird, kann auf den Rückgabewert nur dann zugegriffen werden, wenn der Debugger in Einzelschritten in der aufgerufenen Methode bewegt wird. In vielen Fällen ist dies nicht möglich, insbesondere wenn die aufgerufene Methode in einer externen Bibliothek definiert ist.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 Wenn Sie die [ICorDebugCode3::GetReturnValueLiveOffset-Methode einen IL-Offset](icordebugcode3-getreturnvalueliveoffset-method.md) an eine Funktionsaufrufsite übergeben, werden ein oder mehrere systemeigene Offsets zurückgegeben. In diesem Fall kann der Debugger Haltepunkte für diese systemeigenen Offsets in der Funktion festlegen. Wenn der Debugger auf einen der Haltepunkte trifft, können Sie den gleichen IL-Offset übergeben, den Sie an diese Methode übergeben haben, um den Rückgabewert abzurufen. Der Debugger sollte dann alle von ihm festgelegten Haltepunkte entfernen.  
  
> [!WARNING]
> Mit der [ICorDebugCode3::GetReturnValueLiveOffset-Methode](icordebugcode3-getreturnvalueliveoffset-method.md) und `ICorDebugILFrame3::GetReturnValueForILOffset` -Methoden können Sie Nur Rückgabewertinformationen für Referenztypen abrufen. Das Abrufen von Rückgabewertinformationen für Werttypen wird nicht unterstützt (alle Typen, die von <xref:System.ValueType> abgeleitet werden).  
  
 Der vom `ILOffset` Parameter angegebene IL-Offset sollte sich an einer Funktionseinaufrufsite befinden, und das Debuggee sollte an einem Breakpoint-Satz am systemeigenen Offset angehalten werden, der von der [ICorDebugCode3::GetReturnValueLiveOffset-Methode](icordebugcode3-getreturnvalueliveoffset-method.md) für denselben IL-Offset zurückgegeben wird. Wenn die zu debuggende Komponente nicht an der korrekten Position für den festgelegten IL-Offset angehalten wird, schlägt die API fehl.  
  
 Wenn der Funktionsaufruf keinen Wert zurückgibt, schlägt die API fehl.  
  
 Die `ICorDebugILFrame3::GetReturnValueForILOffset`-Methode ist nur auf x86- und AMD64-basierten Systemen verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetReturnValueLiveOffset-Methode](icordebugcode3-getreturnvalueliveoffset-method.md)
- [ICorDebugILFrame3-Schnittstelle](icordebugilframe3-interface.md)
