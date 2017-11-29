---
title: ICorDebugProcess6::EnableVirtualModuleSplitting-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d6e1f459636f1bb2b3844eebdb98bebd1deb73cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a>ICorDebugProcess6::EnableVirtualModuleSplitting-Methode
Aktiviert oder deaktiviert die virtuelle Modulteilung.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `enableSplitting`  
 `true`, um die virtuelle Modulteilung zu aktivieren; `false`, um sie zu deaktivieren.  
  
## <a name="remarks"></a>Hinweise  
 Virtueller Module [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) , Module, die während des Erstellungsvorgangs zusammengeführt wurden verarbeitet und stellt sie als eine Gruppe von separaten Modulen und nicht als ein einziges großes Modul zu erkennen. Hierdurch ändert sich das Verhalten der verschiedenen [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) unten beschriebenen Methoden.  
  
> [!NOTE]
>  Diese Methode ist nur in Verbindung mit .NET Native verfügbar.  
  
 Diese Methode ist aufrufbar, und der `enableSplitting`-Wert kann jederzeit geändert werden. Bewirkt keine zustandsbehafteten funktionalen Änderungen in einer [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) -Objekt, abgesehen von der Änderung des Verhaltens der aufgeführten Methoden der [aufteilen virtueller Module und der nicht verwalteten Debug-APIs](#APIs) Der Abschnitt zu dem Zeitpunkt, die sie aufgerufen werden. Die Verwendung virtueller Module führt beim Aufrufen dieser Methoden durchaus zu Leistungseinbußen. Darüber hinaus erhebliche im Arbeitsspeicher Zwischenspeichern die virtualisierten Metadaten gegebenenfalls korrekt implementieren die [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -APIs und die speicherungen möglicherweise beibehalten, auch nachdem Teilen virtueller Module deaktiviert wurde.  
  
## <a name="terminology"></a>Terminologie  
 Die folgenden Begriffe werden verwendet, um das Teilen virtueller Module zu beschreiben:  
  
 Container-Module oder Container  
 Die aggregierten Module.  
  
 Untergeordnete Module oder virtuelle Module  
 Die Module, die sich in einem Container befinden.  
  
 reguläre Module  
 Module, die zur Zeit der Erstellung nicht zusammengeführt wurden. Hierbei handelt es sich weder um Containermodule noch um untergeordnete Module.  
  
 Containermodule und untergeordnete Module werden durch ICorDebugModule-Schnittstellenobjekte dargestellt. Das Verhalten der Benutzeroberfläche ist jedoch in jedem Fall etwas anders als die \<X-Ref Abschnitt > Abschnitt wird beschrieben.  
  
## <a name="modules-and-assemblies"></a>Module und Assemblys  
 Assemblys mit mehreren Modulen werden nicht bei Zusammenführungen nicht unterstützt, somit stehen ein Modul und eine Assembly im Verhältnis 1:1. Jedes ICorDebugModule-Objekt, unabhängig davon, ob es sich um ein Container-Modul oder ein untergeordnetes Modul darstellt verfügt über ein entsprechendes ICorDebugAssembly-Objekt. Die [ICorDebugModule:: GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) Methode, die aus dem Modul der Assembly konvertiert. In der anderen Richtung Zuordnen der [ICorDebugAssembly:: EnumerateModules](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md) -Methode nur 1-Modul aufgeführt. Da Assembly und Modul in diesem Fall eng miteinander verknüpft sind, sind die Begriffe Assembly und Modul weitgehend austauschbar.  
  
## <a name="behavioral-differences"></a>Verhaltensunterschiede  
 Container-Module weisen folgende Verhaltensweisen und Merkmale auf:  
  
-   Die Metadaten sind für alle enthaltenen untergeordneten Module zusammengeführt.  
  
-   Ihre Typennamen können geändert werden.  
  
-   Die [ICorDebugModule:: GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) Methode übergibt den Pfad an ein Modul auf dem Datenträger.  
  
-   Die [ICorDebugModule:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) -Methode gibt die Größe des Bildes.  
  
-   Mit der ICorDebugAssembly3.EnumerateContainedAssemblies-Methode werden die untergeordneten Module aufgeführt.  
  
-   Mit der ICorDebugAssembly3.GetContainerAssembly-Methode wird `S_FALSE` ausgegeben.  
  
 Untergeordnete Container-Module weisen folgende Verhaltensweisen und Merkmale auf:  
  
-   Sie verfügen über einen reduzierten Satz von Metadaten, der sich nur auf die ursprünglich zugsammengeführte Assembly bezieht.  
  
-   Die Metadatennamen werden nicht geändert.  
  
-   Die Metadatentoken entsprechen wahrscheinlich nicht den Token in der ursprünglichen Baugruppe vor dem Merge im Erstellungsprozess.  
  
-   Die [ICorDebugModule:: GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md) Methodenrückgabe den Assemblynamen und keinen Dateipfad.  
  
-   Die [ICorDebugModule:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md) Methodenrückgabe die ursprüngliche Bildgröße.  
  
-   Mit der ICorDebugAssembly3.GetContainerAssemblies-Methode wird `S_FALSE` ausgegeben.  
  
-   Die ICorDebugAssembly3.GetContainerAssembly-Methode gibt das enthaltende Modul aus.  
  
## <a name="interfaces-retrieved-from-modules"></a>Aus Modulen abgerufene Schnittstellen  
 Es können verschiedene Schnittstellen erstellt oder aus Modulen abgerufen werden. Hierzu zählen:  
  
-   Ein ICorDebugClass-Objekt, das vom ist die [ICorDebugModule:: GetClassFromToken](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md) Methode.  
  
-   Ein ICorDebugAssembly-Objekt, das vom ist die [ICorDebugModule:: GetAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md) Methode.  
  
 Diese Objekte werden stets von zwischengespeichert [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md), und sie weisen die gleiche zeigeridentität unabhängig davon, ob sie erstellt oder aus dem containermodul oder einem untergeordneten Modul abgefragt wurden. Das untergeordnete Modul bietet eine gefilterte Ansicht dieser zwischengespeicherten Objekte, jedoch keinen separaten Cache mit eigenen Kopien.  
  
<a name="APIs"></a>   
## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a>Teilen virtueller Module und nicht verwalteter Debug-APIs  
 In der folgende Tabelle wird gezeigt, wie sich das Teilen virtueller Module auf das Verhalten anderer Methoden in der nicht verwalteten Debug-API auswirkt.  
  
|Methode|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[ICorDebugFunction:: GetModule](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|Gibt das untergeordnete Modul aus, in dem diese Funktion ursprünglich definiert wurde|Gibt das Containermodul zurück, mit dem diese Funktion zusammengeführt wurde|  
|[ICorDebugClass:: GetModule](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|Gibt das untergeordnete Modul aus, in dem diese Klasse ursprünglich definiert wurde.|Gibt das Containermodul aus, mit dem diese Klasse zusammengeführt wurde.|  
|ICorDebugModuleDebugEvent::GetModule|Gibt das Containermodul aus, das geladen wurde. Untergeordnete Module erhalten unabhängig von dieser Einstellung keine Ladeereignisse.|Gibt das Containermodul aus, das geladen wurde.|  
|[ICorDebugAppDomain:: EnumerateAssemblies](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-enumerateassemblies-method.md)|Gibt eine Liste aller untergeordneten und regulären Assemblys aus; Container-Assemblys sind nicht enthalten. **Hinweis:** Container-Assembly Symbole fehlen, ohne die untergeordneten Assemblys aufgezählt werden. Wenn in einer regulären Baugruppe Symbole fehlen, kann die Auflistung u.U. erfolgen.|Gibt eine Liste der Container-Assemblys und regulären Assemblys aus; untergeordnete Assemblys sind nicht enthalten. **Hinweis:** eine reguläre Baugruppe Symbole fehlen, kann bzw. können nicht aufgezählt werden.|  
|[ICorDebugCode:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md) (wenn es sich um eine auf reinen IL-Code verwiesen wird)|Gibt die IL aus, die in einem Assemblybild vor dem Merge gültig wäre. Insbesondere werden Inline-Metadatentoken korrekt zu TypeRef-Token oder MemberRef-Token, wenn die Typen, auf die verwiesen wird, nicht im virtuellen Modul definiert werden, das den IL-Code enthält. Diese TypeRef-Token oder MemberRef-Token können nachgeschlagen werden die [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Objekt für die entsprechenden virtuellen ICorDebugModule-Objekt.|Gibt die IL im Assemblybild nach dem Merge aus.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugProcess6-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
