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
ms.openlocfilehash: 7a96385ccc6e7f9089365c19bb8f150015bba81c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788530"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>ICorDebugILFrame3::GetReturnValueForILOffset-Methode
Ruft ein ICorDebug Value-Objekt ab, das den Rückgabewert einer Funktion kapselt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ILOffset`  
 Der IL-Offset. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 `ppReturnValue`  
 Ein Zeiger auf die Adresse eines ICorDebugValue-Schnittstellen Objekts, das Informationen über den Rückgabewert eines Funktions Aufrufes bereitstellt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird zusammen mit der [ICorDebugCode3:: getreturnvalueliveoffset](icordebugcode3-getreturnvalueliveoffset-method.md) -Methode verwendet, um den Rückgabewert einer Methode zu erhalten. Dies ist für Methoden sehr nützlich, deren Rückgabewerte ignoriert wurden, wie in den folgenden beiden Codebeispielen dargestellt. Im ersten Beispiel wird die <xref:System.Int32.TryParse%2A?displayProperty=nameWithType>-Methode aufgerufen, der Rückgabewert der Methode jedoch ignoriert.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 Das zweite Beispiel veranschaulicht ein allgemeineres Problem beim Debuggen. Da eine Methode als Argument eines Methodenaufrufs verwendet wird, kann auf den Rückgabewert nur dann zugegriffen werden, wenn der Debugger in Einzelschritten in der aufgerufenen Methode bewegt wird. In vielen Fällen ist dies nicht möglich, insbesondere wenn die aufgerufene Methode in einer externen Bibliothek definiert ist.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 Wenn Sie die [ICorDebugCode3:: getreturnvalueliveoffset](icordebugcode3-getreturnvalueliveoffset-method.md) -Methode einem IL-Offset an eine Funktions Aufrufsite übergeben, wird mindestens ein System eigenes Offset zurückgegeben. In diesem Fall kann der Debugger Haltepunkte für diese systemeigenen Offsets in der Funktion festlegen. Wenn der Debugger auf einen der Haltepunkte trifft, können Sie den gleichen IL-Offset übergeben, den Sie an diese Methode übergeben haben, um den Rückgabewert abzurufen. Der Debugger sollte dann alle von ihm festgelegten Haltepunkte entfernen.  
  
> [!WARNING]
> Die [ICorDebugCode3:: getreturnvalueliveoffset-Methode](icordebugcode3-getreturnvalueliveoffset-method.md) und die `ICorDebugILFrame3::GetReturnValueForILOffset`-Methoden ermöglichen es Ihnen, Rückgabewert Informationen nur für Verweis Typen zu erhalten. Das Abrufen von Rückgabewertinformationen für Werttypen wird nicht unterstützt (alle Typen, die von <xref:System.ValueType> abgeleitet werden).  
  
 Der durch den `ILOffset`-Parameter angegebene IL-Offset sollte sich an einer Funktions Aufrufsite befinden, und die zu debuggende Komponente sollte an einem Haltepunkt angehalten werden, der bei dem systemeigenen Offset festgelegt wird, der von der [ICorDebugCode3:: getreturnvalueliveoffset](icordebugcode3-getreturnvalueliveoffset-method.md) -Methode für den gleichen IL-Offset Wenn die zu debuggende Komponente nicht an der korrekten Position für den festgelegten IL-Offset angehalten wird, schlägt die API fehl.  
  
 Wenn der Funktionsaufruf keinen Wert zurückgibt, schlägt die API fehl.  
  
 Die `ICorDebugILFrame3::GetReturnValueForILOffset`-Methode ist nur auf x86- und AMD64-basierten Systemen verfügbar.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetReturnValueLiveOffset-Methode](icordebugcode3-getreturnvalueliveoffset-method.md)
- [ICorDebugILFrame3-Schnittstelle](icordebugilframe3-interface.md)
