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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ac90473a0bf15173683c45abc8e4a840ea7e733
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946432"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>ICorDebugILFrame3::GetReturnValueForILOffset-Methode
Ruft ein "ICorDebugValue"-Objekt, das den Rückgabewert einer Funktion kapselt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ILOffset`  
 Der IL-Offset. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 `ppReturnValue`  
 Ein Zeiger auf die Adresse der Schnittstelle "ICorDebugValue"-Objekts, das Informationen über den Rückgabewert eines Funktionsaufrufs bereitstellt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird verwendet, zusammen mit den [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) Methode, um den Rückgabewert einer Methode abzurufen. Dies ist für Methoden sehr nützlich, deren Rückgabewerte ignoriert wurden, wie in den folgenden beiden Codebeispielen dargestellt. Im ersten Beispiel wird die <xref:System.Int32.TryParse%2A?displayProperty=nameWithType>-Methode aufgerufen, der Rückgabewert der Methode jedoch ignoriert.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 Das zweite Beispiel veranschaulicht ein allgemeineres Problem beim Debuggen. Da eine Methode als Argument eines Methodenaufrufs verwendet wird, kann auf den Rückgabewert nur dann zugegriffen werden, wenn der Debugger in Einzelschritten in der aufgerufenen Methode bewegt wird. In vielen Fällen ist dies nicht möglich, insbesondere wenn die aufgerufene Methode in einer externen Bibliothek definiert ist.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 Wenn Sie übergeben die [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) -Methode ein IL-Offsets an eine funktionsaufrufsite, gibt eine oder mehrere systemeigene Offsets zurück. In diesem Fall kann der Debugger Haltepunkte für diese systemeigenen Offsets in der Funktion festlegen. Wenn der Debugger auf einen der Haltepunkte trifft, können Sie den gleichen IL-Offset übergeben, den Sie an diese Methode übergeben haben, um den Rückgabewert abzurufen. Der Debugger sollte dann alle von ihm festgelegten Haltepunkte entfernen.  
  
> [!WARNING]
>  Die [icordebugcode3:: Getreturnvalueliveoffset-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) und `ICorDebugILFrame3::GetReturnValueForILOffset` Methoden ermöglichen es Ihnen, Rückgabewertinformationen nur für Verweistypen abzurufen. Das Abrufen von Rückgabewertinformationen für Werttypen wird nicht unterstützt (alle Typen, die von <xref:System.ValueType> abgeleitet werden).  
  
 Der IL-Offset innerhalb der `ILOffset` Parameter an eine funktionsaufrufsite sein soll, und die zu debuggende Komponente muss beendet werden, an einem Haltepunkt festlegen, mit dem nativen Offset vom die [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) Methode für den gleichen IL-Offset. Wenn die zu debuggende Komponente nicht an der korrekten Position für den festgelegten IL-Offset angehalten wird, schlägt die API fehl.  
  
 Wenn der Funktionsaufruf keinen Wert zurückgibt, schlägt die API fehl.  
  
 Die `ICorDebugILFrame3::GetReturnValueForILOffset`-Methode ist nur auf x86- und AMD64-basierten Systemen verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetReturnValueLiveOffset-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)
- [ICorDebugILFrame3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
