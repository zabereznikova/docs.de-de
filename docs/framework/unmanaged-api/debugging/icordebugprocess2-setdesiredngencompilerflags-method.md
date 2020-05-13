---
title: ICorDebugProcess2::SetDesiredNGENCompilerFlags-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
ms.openlocfilehash: 366a48e5f6abd92f0c6f796f40bdd263181da4a8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213477"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>ICorDebugProcess2::SetDesiredNGENCompilerFlags-Methode
Legt die Flags fest, die in ein vorkompiliertes Bild eingebettet werden müssen, damit die Common Language Runtime dieses Bild in den aktuellen Prozess lädt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pdwFlags`  
 in Ein Wert der [corentbugjitcompilerflags](cordebugjitcompilerflags-enumeration.md) -Enumeration, der die Compilerflags angibt, die zum Auswählen des richtigen vorkompilierten Bilds verwendet werden.  
  
## <a name="remarks"></a>Hinweise  
 Die- `SetDesiredNGENCompilerFlags` Methode gibt die Flags an, die in ein vorkompiliertes Bild eingebettet werden müssen, damit die Laufzeit dieses Bild in diesen Prozess lädt. Die von dieser Methode festgelegten Flags werden nur zur Auswahl des richtigen vorkompilierten Bilds verwendet. Wenn kein solches Image vorhanden ist, lädt die Runtime stattdessen das MSIL-Image (Microsoft Intermediate Language) und den JIT-Compiler (Just-in-Time). In diesem Fall muss der Debugger weiterhin die [ICorDebugModule2:: SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) -Methode verwenden, um die Flags für die JIT-Kompilierung wie gewünscht festzulegen.  
  
 Wenn ein Bild geladen wird, aber einige JIT-Kompilierungen für dieses Bild stattfinden müssen (Dies ist der Fall, wenn das Image Generika enthält), gelten die von der-Methode angegebenen Compilerflags für `SetDesiredNGENCompilerFlags` die zusätzliche JIT-Kompilierung.  
  
 Die- `SetDesiredNGENCompilerFlags` Methode muss während des Rückrufs von [ICorDebugManagedCallback:: deateprocess](icordebugmanagedcallback-createprocess-method.md) aufgerufen werden. Versuche, die Methode anschließend aufzurufen, können `SetDesiredNGENCompilerFlags` nicht ausgeführt werden. Außerdem schlagen Versuche, Flags festzulegen, die entweder nicht in der- `CorDebugJITCompilerFlags` Enumeration definiert sind oder für den angegebenen Prozess nicht zulässig sind, fehl.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](icordebug-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
