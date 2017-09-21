---
title: JIT-ETW-Ablaufverfolgungsereignisse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JIT tracing events [.NET Framework]
- ETW, JIT tracing events (CLR)
ms.assetid: 926adde2-c123-452e-bf4f-4b977bf06ffb
caps.latest.revision: 8
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b33a86eb235524ed9cbe5e07dd6625fedf884411
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="jit-tracing-etw-events"></a>JIT-ETW-Ablaufverfolgungsereignisse
<a name="top"></a> Diese Ereignisse sammeln Informationen über den Erfolg oder Misserfolg des Just-In-Time (JIT)-Inlining und der JIT-Endaufrufe.  
  
 JIT-Ablaufverfolgungsereignisse bestehen aus den folgenden beiden Kategorien:  
  
-   [JIT-Inliningereignisse](#jit_inlining_events)  
  
-   [JIT-Endaufrufereignisse](#jit_tail_call_events)  
  
<a name="jit_inlining_events"></a>   
## <a name="jit-inlining-events"></a>JIT-Inliningereignisse  
  
### <a name="methodjitinliningfailed-event"></a>MethodJitInliningFailed-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an. (Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`JITTracingKeyword` (0x10)|Ausführlich (5)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`MethodJitInliningFailed`|186|Das JIT-Inlining ist fehlgeschlagen.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|MethodBeingCompiledNameSpace|win:UnicodeString|Der Namespace der Methode, die kompiliert wird.|  
|MethodBeingCompiledName|win:UnicodeString|Der Name der Methode, die kompiliert wird.|  
|MethodBeingCompiledNameSignature|win:UnicodeString|Die Signatur der Methode, die kompiliert wird.|  
|InlinerNamespace|win:UnicodeString|Der Namespace der Methode, für die der JIT-Compiler versucht, Code zu generieren.|  
|InlinerName|win:UnicodeString|Der Name der Methode, für die der Compiler versucht, Code zu generieren. Er ist möglicherweise nicht identisch mit `MethodBeingCompiledName` , wenn der Compiler versucht, Inlinecode in `MethodBeingCompiledName` einzufügen, statt einen Aufruf von `InlinerName`zu generieren.|  
|InlinerNameSignature|win:UnicodeString|Die Signatur des Inliners:|  
|InlineeNamespace|win:UnicodeString|Der Namespace des Inlinees.|  
|InlineeName|win:UnicodeString|Die Methode, die der Compiler Inline setzen möchte (es wird kein Aufruf generiert).|  
|InlineeNameSignature|win:UnicodeString|Die Signatur des Inlinees:|  
|FailAlways|win:Boolean|Ein Hinweis für den JIT-Compiler, dass Inlining für den Inlinee immer einen Fehler verursacht.|  
|FailReason|win:UnicodeString|INLINE_NEVER bedeutet, dass ein vorheriger Versuch des Inlining bestimmt hat, dass Inlining aus einem anderen Grund nie erfolgreich sein wird; andernfalls Freiformtext.|  
|ClrInstanceID|win:UnicodeString|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
### <a name="methodjitinliningsucceeded-event"></a>MethodJitInliningSucceeded-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`JITTracingKeyword` (0x10)|Ausführlich (5)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`MethodJitInliningSucceeded`|185|Das Methoden-Inlining war erfolgreich.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|MethodBeingCompiledNameSpace|win:UnicodeString|Der Namespace der Methode, die kompiliert wird.|  
|MethodBeingCompiledName|win:UnicodeString|Der Name der Methode, die kompiliert wird.|  
|MethodBeingCompiledNameSignature|win:UnicodeString|Die Signatur der Methode, die kompiliert wird.|  
|InlinerNamespace|win:UnicodeString|Der Namespace der Methode, für die der JIT-Compiler versucht, Code zu generieren.|  
|InlinerName|win:UnicodeString|Der Name der Methode, für die der Compiler versucht, Code zu generieren. Er ist möglicherweise nicht identisch mit `MethodBeingCompiledName` , wenn der Compiler versucht, Inlinecode in `MethodBeingCompiledName` einzufügen, statt einen Aufruf von `InlinerName`zu generieren.|  
|InlinerNameSignature|win:UnicodeString|Die Signatur des Inliners:|  
|InlineeNamespace|win:UnicodeString|Der Namespace des Inlinees.|  
|InlineeName|win:UnicodeString|Die Methode, die der Compiler Inline setzen möchte (es wird kein Aufruf generiert).|  
|InlineeNameSignature|win:UnicodeString|Die Signatur des Inlinees:|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
 [Zurück nach oben](#top)  
  
<a name="jit_tail_call_events"></a>   
## <a name="jit-tail-call-events"></a>JIT-Endaufrufereignisse  
  
### <a name="methodjittailcallfailed-event"></a>MethodJITTailCallFailed-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`JITTracingKeyword` (0x10)|Ausführlich (5)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`MethodJitTailCallFailed`|189|Fehler beim Methodenendaufruf.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|MethodBeingCompiledNameSpace|win:UnicodeString|Der Namespace der Methode, die kompiliert wird.|  
|MethodBeingCompiledName|win:UnicodeString|Der Name der Methode, die kompiliert wird.|  
|MethodBeingCompiledNameSignature|win:UnicodeString|Die Signatur der Methode, die kompiliert wird.|  
|CallerNamespace|win:UnicodeString|Der Namespace der Methode, für die der JIT-Compiler versucht, Code zu generieren.|  
|CallerName|win:UnicodeString|Der Name der Methode, für die der Compiler versucht, Code zu generieren.|  
|CallerNameSignature|win:UnicodeString|Die Signatur des Aufrufers.|  
|CalleeNamespace|win:UnicodeString|Der Namespace des Aufgerufenen.|  
|CalleeName|win:UnicodeString|Die Methode, die der Compiler auf Endaufruf setzen möchte (es wird kein Aufruf generiert).|  
|CalleeNameSignature|win:UnicodeString|Die Signatur des Aufgerufenen.|  
|TailPrefix|win:Boolean|Das Präfix für den Endaufruf.|  
|FailReason|win:UnicodeString|Der Grund für den Fehler des Endaufrufs.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
### <a name="methodjittailcallsucceeded-event"></a>MethodJITTailCallSucceeded-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`JITTracingKeyword` (0x10)|Ausführlich (5)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`MethodJitTailCallSucceeded`|188|Der Methodenendaufruf war erfolgreich.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|MethodBeingCompiledNameSpace|win:UnicodeString|Der Namespace der Methode, die kompiliert wird.|  
|MethodBeingCompiledName|win:UnicodeString|Der Name der Methode, die kompiliert wird.|  
|MethodBeingCompiledNameSignature|win:UnicodeString|Die Signatur der Methode, die kompiliert wird.|  
|CallerNamespace|win:UnicodeString|Der Namespace der Methode, für die der JIT-Compiler versucht, Code zu generieren.|  
|CallerName|win:UnicodeString|Der Name der Methode, für die der Compiler versucht, Code zu generieren.|  
|CallerNameSignature|win:UnicodeString|Die Signatur des Aufrufers.|  
|CalleeNamespace|win:UnicodeString|Der Namespace des Aufgerufenen.|  
|CalleeName|win:UnicodeString|Die Methode, die der Compiler auf Endaufruf setzen möchte (es wird kein Aufruf generiert).|  
|CalleeNameSignature|win:UnicodeString|Die Signatur des Aufgerufenen.|  
|TailPrefix|win:Boolean|Das Präfix für den Endaufruf.|  
|TailCallType|win:UnicodeString|Der Typ des Endaufrufs.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
## <a name="see-also"></a>Siehe auch  
 [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md)

