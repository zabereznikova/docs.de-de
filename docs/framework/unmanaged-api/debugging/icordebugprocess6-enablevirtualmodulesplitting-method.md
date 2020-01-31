---
title: ICorDebugProcess6::EnableVirtualModuleSplitting-Methode
ms.date: 03/30/2017
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
ms.openlocfilehash: 224acc9ed61bc2753a5e763dd2c3d4af63300d64
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792260"
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a>ICorDebugProcess6::EnableVirtualModuleSplitting-Methode
Aktiviert oder deaktiviert die virtuelle Modulteilung.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `enableSplitting`  
 `true`, um die virtuelle Modulteilung zu aktivieren; `false`, um sie zu deaktivieren.  
  
## <a name="remarks"></a>Hinweise  
 Durch die Aufteilung virtueller Module erkennt [ICorDebug](icordebug-interface.md) Module, die während des Buildprozesses zusammengeführt wurden, und stellt Sie als eine Gruppe von separaten Modulen anstelle eines einzelnen großen Moduls dar. Dadurch wird das Verhalten der verschiedenen [ICorDebug](icordebug-interface.md) -Methoden geändert, die unten beschrieben werden.  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
 Diese Methode ist aufrufbar, und der `enableSplitting`-Wert kann jederzeit geändert werden. Sie verursacht keine Zustands behafteten funktionalen Änderungen in einem [ICorDebug](icordebug-interface.md) -Objekt, außer das Ändern des Verhaltens der Methoden, die in der [Aufteilung virtueller Module und der nicht verwalteten Debug-APIs](#APIs) zum Zeitpunkt des Aufrufs aufgeführt sind. Die Verwendung virtueller Module führt beim Aufrufen dieser Methoden durchaus zu Leistungseinbußen. Außerdem ist möglicherweise ein signifikantes in-Memory-Caching der virtualisierten Metadaten erforderlich, um die [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -APIs ordnungsgemäß zu implementieren. Diese Caches können auch nach der Deaktivierung der virtuellen Modul Aufteilung beibehalten werden.  
  
## <a name="terminology"></a>Terminologie  
 Die folgenden Begriffe werden verwendet, um das Teilen virtueller Module zu beschreiben:  
  
 Container-Module oder Container  
 Die aggregierten Module.  
  
 Untergeordnete Module oder virtuelle Module  
 Die Module, die sich in einem Container befinden.  
  
 reguläre Module  
 Module, die zur Zeit der Erstellung nicht zusammengeführt wurden. Hierbei handelt es sich weder um Containermodule noch um untergeordnete Module.  
  
 Containermodule und untergeordnete Module werden durch ICorDebugModule-Oberflächenobjekte dargestellt. Das Verhalten der-Schnittstelle unterscheidet sich jedoch in jedem Fall geringfügig, wie im Abschnitt \<x-ref to section > beschrieben.  
  
## <a name="modules-and-assemblies"></a>Module und Assemblys  
 Assemblys mit mehreren Modulen werden nicht bei Zusammenführungen nicht unterstützt, somit stehen ein Modul und eine Assembly im Verhältnis 1:1. Zu jedem ICorDebugModule -Objekt gibt es ein entsprechendes ICorDebugAssembly-Objekt, unabhängig davon, ob es ein Container-Modul oder ein untergeordnetes Modul darstellt. Die [ICorDebugModule:: GetAssembly](icordebugmodule-getassembly-method.md) -Methode konvertiert vom Modul in die Assembly. Um in der anderen Richtung zuzuordnen, listet die [ICorDebugAssembly:: EnumerateModules](icordebugassembly-enumeratemodules-method.md) -Methode nur ein Modul auf. Da Assembly und Modul in diesem Fall eng miteinander verknüpft sind, sind die Begriffe Assembly und Modul weitgehend austauschbar.  
  
## <a name="behavioral-differences"></a>Verhaltensunterschiede  
 Container-Module weisen folgende Verhaltensweisen und Merkmale auf:  
  
- Die Metadaten sind für alle enthaltenen untergeordneten Module zusammengeführt.  
  
- Ihre Typennamen können geändert werden.  
  
- Die [ICorDebugModule:: GetName](icordebugmodule-getname-method.md) -Methode gibt den Pfad zu einem Modul auf dem Datenträger zurück.  
  
- Die [ICorDebugModule:: GetSize](icordebugmodule-getsize-method.md) -Methode gibt die Größe des Bilds zurück.  
  
- Mit der ICorDebugAssembly3.EnumerateContainedAssemblies-Methode werden die untergeordneten Module aufgeführt.  
  
- Mit der ICorDebugAssembly3.GetContainerAssembly-Methode wird `S_FALSE` ausgegeben.  
  
 Untergeordnete Container-Module weisen folgende Verhaltensweisen und Merkmale auf:  
  
- Sie verfügen über einen reduzierten Satz von Metadaten, der sich nur auf die ursprünglich zugsammengeführte Assembly bezieht.  
  
- Die Metadatennamen werden nicht geändert.  
  
- Die Metadatentoken entsprechen wahrscheinlich nicht den Token in der ursprünglichen Baugruppe vor dem Merge im Erstellungsprozess.  
  
- Die [ICorDebugModule:: GetName](icordebugmodule-getname-method.md) -Methode gibt den Assemblynamen und keinen Dateipfad zurück.  
  
- Die [ICorDebugModule:: GetSize](icordebugmodule-getsize-method.md) -Methode gibt die ursprüngliche Größe des nicht zusammengeführten Bilds zurück.  
  
- Mit der ICorDebugAssembly3.GetContainerAssemblies-Methode wird `S_FALSE` ausgegeben.  
  
- Die ICorDebugAssembly3.GetContainerAssembly-Methode gibt das enthaltende Modul aus.  
  
## <a name="interfaces-retrieved-from-modules"></a>Aus Modulen abgerufene Schnittstellen  
 Es können verschiedene Schnittstellen erstellt oder aus Modulen abgerufen werden. Hierzu zählen:  
  
- Ein ICorDebugClass-Objekt, das von der [ICorDebugModule:: GetClassFromToken](icordebugmodule-getclassfromtoken-method.md) -Methode zurückgegeben wird.  
  
- Ein ICorDebugAssembly-Objekt, das von der [ICorDebugModule:: GetAssembly](icordebugmodule-getassembly-method.md) -Methode zurückgegeben wird.  
  
 Diese Objekte werden immer von [ICorDebug](icordebug-interface.md)zwischengespeichert und weisen die gleiche Zeiger Identität auf, unabhängig davon, ob Sie vom Containermodul oder einem Untermodul erstellt oder abgefragt wurden. Das untergeordnete Modul bietet eine gefilterte Ansicht dieser zwischengespeicherten Objekte, jedoch keinen separaten Cache mit eigenen Kopien.  
  
<a name="APIs"></a>   
## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a>Teilen virtueller Module und nicht verwalteter Debug-APIs  
 In der folgende Tabelle wird gezeigt, wie sich das Teilen virtueller Module auf das Verhalten anderer Methoden in der nicht verwalteten Debug-API auswirkt.  
  
|-Methode|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[ICorDebugFunction::GetModule](icordebugfunction-getmodule-method.md)|Gibt das untergeordnete Modul aus, in dem diese Funktion ursprünglich definiert wurde|Gibt das Containermodul zurück, mit dem diese Funktion zusammengeführt wurde|  
|[ICorDebugClass::GetModule](icordebugclass-getmodule-method.md)|Gibt das untergeordnete Modul aus, in dem diese Klasse ursprünglich definiert wurde.|Gibt das Containermodul aus, mit dem diese Klasse zusammengeführt wurde.|  
|ICorDebugModuleDebugEvent::GetModule|Gibt das Containermodul aus, das geladen wurde. Untergeordnete Module erhalten unabhängig von dieser Einstellung keine Ladeereignisse.|Gibt das Containermodul aus, das geladen wurde.|  
|[ICorDebugAppDomain::EnumerateAssemblies](icordebugappdomain-enumerateassemblies-method.md)|Gibt eine Liste aller untergeordneten und regulären Assemblys aus; Container-Assemblys sind nicht enthalten. **Hinweis:**  Wenn in einer containerassembly Symbole fehlen, wird keine der zugehörigen untergeordneten Assemblys aufgelistet. Wenn in einer regulären Baugruppe Symbole fehlen, kann die Auflistung u.U. erfolgen.|Gibt eine Liste der Container-Assemblys und regulären Assemblys aus; untergeordnete Assemblys sind nicht enthalten. **Hinweis:**  Wenn in einer regulären Assembly Symbole fehlen, kann diese nicht aufgelistet werden.|  
|[ICorDebugCode:: GetCode](icordebugcode-getcode-method.md) (nur bei verweisen auf IL-Code)|Gibt die IL aus, die in einem Assemblybild vor dem Merge gültig wäre. Insbesondere werden Inline-Metadatentoken korrekt zu TypeRef-Token oder MemberRef-Token, wenn die Typen, auf die verwiesen wird, nicht im virtuellen Modul definiert werden, das den IL-Code enthält. Diese TypeRef-oder Mitgliedschafts Token können im [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -Objekt für das entsprechende virtuelle ICorDebug Module-Objekt gesucht werden.|Gibt die IL im Assemblybild nach der Zusammenführung aus.|  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess6-Schnittstelle](icordebugprocess6-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
