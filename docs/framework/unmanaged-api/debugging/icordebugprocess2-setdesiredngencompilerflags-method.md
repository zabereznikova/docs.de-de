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
ms.openlocfilehash: 9f62d94d30c8c4f23073895b8ff0f7afa2dbad6b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792496"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>ICorDebugProcess2::SetDesiredNGENCompilerFlags-Methode
Legt die Flags fest, die in ein vorkompiliertes Bild eingebettet werden müssen, damit die Common Language Runtime dieses Bild in den aktuellen Prozess lädt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pdwFlags`  
 in Ein Wert der [corentbugjitcompilerflags](cordebugjitcompilerflags-enumeration.md) -Enumeration, der die Compilerflags angibt, die zum Auswählen des richtigen vorkompilierten Bilds verwendet werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `SetDesiredNGENCompilerFlags`-Methode gibt die Flags an, die in ein vorkompiliertes Bild eingebettet werden müssen, damit die Laufzeit dieses Bild in diesen Prozess lädt. Die von dieser Methode festgelegten Flags werden nur zur Auswahl des richtigen vorkompilierten Bilds verwendet. Wenn kein solches Image vorhanden ist, lädt die Runtime stattdessen das MSIL-Image (Microsoft Intermediate Language) und den JIT-Compiler (Just-in-Time). In diesem Fall muss der Debugger weiterhin die [ICorDebugModule2:: SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) -Methode verwenden, um die Flags für die JIT-Kompilierung wie gewünscht festzulegen.  
  
 Wenn ein Bild geladen wird, aber einige JIT-Kompilierungen für dieses Bild stattfinden müssen (Dies ist der Fall, wenn das Image Generika enthält), gelten die von der `SetDesiredNGENCompilerFlags`-Methode angegebenen Compilerflags für die zusätzliche JIT-Kompilierung.  
  
 Die `SetDesiredNGENCompilerFlags`-Methode muss während des [ICorDebugManagedCallback::](icordebugmanagedcallback-createprocess-method.md) -Rückruf aufgerufen werden. Versuche, die `SetDesiredNGENCompilerFlags`-Methode später aufzurufen, schlagen fehl. Außerdem schlagen Versuche, Flags festzulegen, die entweder nicht in der `CorDebugJITCompilerFlags` Enumeration definiert sind oder für den angegebenen Prozess nicht zulässig sind, fehl.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](icordebug-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
