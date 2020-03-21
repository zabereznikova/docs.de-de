---
title: ICorDebugProcess6::EnableVirtualModuleSplitting-Methode
ms.date: 03/30/2017
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
ms.openlocfilehash: 8ad15d11ce81323b30434b3db98259a74a198f29
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178568"
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a>ICorDebugProcess6::EnableVirtualModuleSplitting-Methode
Aktiviert oder deaktiviert die virtuelle Modulteilung.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `enableSplitting`  
 `true`, um die virtuelle Modulteilung zu aktivieren; `false`, um sie zu deaktivieren.  
  
## <a name="remarks"></a>Bemerkungen  
 Die Aufteilung virtueller Module bewirkt, dass [ICorDebug](icordebug-interface.md) Module erkennt, die während des Buildprozesses zusammengeführt wurden, und sie als eine Gruppe separater Module und nicht als einzelnes großes Modul präsentiert. Dadurch wird das Verhalten verschiedener [iCorDebug-Methoden](icordebug-interface.md) geändert, die unten beschrieben werden.  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
 Diese Methode ist aufrufbar, und der `enableSplitting`-Wert kann jederzeit geändert werden. Es verursacht keine zustandsbehafteten funktionalen Änderungen in einem [ICorDebug-Objekt,](icordebug-interface.md) außer das Verhalten der Methoden zu ändern, die im [Abschnitt "Virtuelle Modulaufteilung" und im Abschnitt nicht verwaltete Debugging-APIs](#APIs) zum Zeitpunkt des Aufrufs aufgeführt sind. Die Verwendung virtueller Module führt beim Aufrufen dieser Methoden durchaus zu Leistungseinbußen. Darüber hinaus ist möglicherweise eine signifikante Zwischenspeicherung der virtualisierten Metadaten im Arbeitsspeicher erforderlich, um die [IMetaDataImport-APIs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) korrekt zu implementieren, und diese Caches können auch nach dem Deaktivieren der Aufteilung virtueller Module beibehalten werden.  
  
## <a name="terminology"></a>Begriff  
 Die folgenden Begriffe werden verwendet, um das Teilen virtueller Module zu beschreiben:  
  
 Container-Module oder Container  
 Die aggregierten Module.  
  
 Untergeordnete Module oder virtuelle Module  
 Die Module, die sich in einem Container befinden.  
  
 reguläre Module  
 Module, die zur Zeit der Erstellung nicht zusammengeführt wurden. Hierbei handelt es sich weder um Containermodule noch um untergeordnete Module.  
  
 Containermodule und untergeordnete Module werden durch ICorDebugModule-Oberflächenobjekte dargestellt. Das Verhalten der Schnittstelle ist jedoch in jedem \<Fall etwas anders, wie der Abschnitt x-ref zu Abschnitt> beschreibt.  
  
## <a name="modules-and-assemblies"></a>Module und Assemblys  
 Assemblys mit mehreren Modulen werden nicht bei Zusammenführungen nicht unterstützt, somit stehen ein Modul und eine Assembly im Verhältnis 1:1. Zu jedem ICorDebugModule -Objekt gibt es ein entsprechendes ICorDebugAssembly-Objekt, unabhängig davon, ob es ein Container-Modul oder ein untergeordnetes Modul darstellt. Die [ICorDebugModule::GetAssembly-Methode](icordebugmodule-getassembly-method.md) konvertiert aus dem Modul in die Assembly. Um in die andere Richtung zuzuordnen, zählt die [ICorDebugAssembly::EnumerateModules-Methode](icordebugassembly-enumeratemodules-method.md) nur 1 Modul auf. Da Assembly und Modul in diesem Fall eng miteinander verknüpft sind, sind die Begriffe Assembly und Modul weitgehend austauschbar.  
  
## <a name="behavioral-differences"></a>Verhaltensunterschiede  
 Container-Module weisen folgende Verhaltensweisen und Merkmale auf:  
  
- Die Metadaten sind für alle enthaltenen untergeordneten Module zusammengeführt.  
  
- Ihre Typennamen können geändert werden.  
  
- Die [ICorDebugModule::GetName-Methode](icordebugmodule-getname-method.md) gibt den Pfad an ein On-Disk-Modul zurück.  
  
- Die [ICorDebugModule::GetSize-Methode](icordebugmodule-getsize-method.md) gibt die Größe dieses Abbilds zurück.  
  
- Mit der ICorDebugAssembly3.EnumerateContainedAssemblies-Methode werden die untergeordneten Module aufgeführt.  
  
- Mit der ICorDebugAssembly3.GetContainerAssembly-Methode wird `S_FALSE` ausgegeben.  
  
 Untergeordnete Container-Module weisen folgende Verhaltensweisen und Merkmale auf:  
  
- Sie verfügen über einen reduzierten Satz von Metadaten, der sich nur auf die ursprünglich zugsammengeführte Assembly bezieht.  
  
- Die Metadatennamen werden nicht geändert.  
  
- Die Metadatentoken entsprechen wahrscheinlich nicht den Token in der ursprünglichen Baugruppe vor dem Merge im Erstellungsprozess.  
  
- Die [ICorDebugModule::GetName-Methode](icordebugmodule-getname-method.md) gibt den Assemblynamen und nicht einen Dateipfad zurück.  
  
- Die [ICorDebugModule::GetSize-Methode](icordebugmodule-getsize-method.md) gibt die ursprüngliche nicht zusammengeführte Bildgröße zurück.  
  
- Mit der ICorDebugAssembly3.GetContainerAssemblies-Methode wird `S_FALSE` ausgegeben.  
  
- Die ICorDebugAssembly3.GetContainerAssembly-Methode gibt das enthaltende Modul aus.  
  
## <a name="interfaces-retrieved-from-modules"></a>Aus Modulen abgerufene Schnittstellen  
 Es können verschiedene Schnittstellen erstellt oder aus Modulen abgerufen werden. Dazu zählen:  
  
- Ein ICorDebugClass-Objekt, das von der [ICorDebugModule::GetClassFromToken-Methode](icordebugmodule-getclassfromtoken-method.md) zurückgegeben wird.  
  
- Ein ICorDebugAssembly-Objekt, das von der [ICorDebugModule::GetAssembly-Methode](icordebugmodule-getassembly-method.md) zurückgegeben wird.  
  
 Diese Objekte werden immer von [ICorDebug](icordebug-interface.md)zwischengespeichert und haben dieselbe Zeigeridentität, unabhängig davon, ob sie aus dem Containermodul oder einem Untermodul erstellt oder abgefragt wurden. Das untergeordnete Modul bietet eine gefilterte Ansicht dieser zwischengespeicherten Objekte, jedoch keinen separaten Cache mit eigenen Kopien.  
  
<a name="APIs"></a>
## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a>Teilen virtueller Module und nicht verwalteter Debug-APIs  
 In der folgende Tabelle wird gezeigt, wie sich das Teilen virtueller Module auf das Verhalten anderer Methoden in der nicht verwalteten Debug-API auswirkt.  
  
|Methode|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[ICorDebugFunction::GetModule](icordebugfunction-getmodule-method.md)|Gibt das untergeordnete Modul aus, in dem diese Funktion ursprünglich definiert wurde|Gibt das Containermodul zurück, mit dem diese Funktion zusammengeführt wurde|  
|[ICorDebugClass::GetModule](icordebugclass-getmodule-method.md)|Gibt das untergeordnete Modul aus, in dem diese Klasse ursprünglich definiert wurde.|Gibt das Containermodul aus, mit dem diese Klasse zusammengeführt wurde.|  
|ICorDebugModuleDebugEvent::GetModule|Gibt das Containermodul aus, das geladen wurde. Untergeordnete Module erhalten unabhängig von dieser Einstellung keine Ladeereignisse.|Gibt das Containermodul aus, das geladen wurde.|  
|[ICorDebugAppDomain::EnumerateAssemblies](icordebugappdomain-enumerateassemblies-method.md)|Gibt eine Liste aller untergeordneten und regulären Assemblys aus; Container-Assemblys sind nicht enthalten. **Hinweis:**  Wenn einer Containerassembly Symbole fehlen, wird keine ihrer Unterbaugruppen aufgezählt. Wenn in einer regulären Baugruppe Symbole fehlen, kann die Auflistung u.U. erfolgen.|Gibt eine Liste der Container-Assemblys und regulären Assemblys aus; untergeordnete Assemblys sind nicht enthalten. **Hinweis:**  Wenn eine reguläre Baugruppe Symbole fehlt, kann sie aufgezählt werden oder auch nicht.|  
|[ICorDebugCode::GetCode](icordebugcode-getcode-method.md) (nur bei Verweis auf IL-Code)|Gibt die IL aus, die in einem Assemblybild vor dem Merge gültig wäre. Insbesondere werden Inline-Metadatentoken korrekt zu TypeRef-Token oder MemberRef-Token, wenn die Typen, auf die verwiesen wird, nicht im virtuellen Modul definiert werden, das den IL-Code enthält. Diese TypeRef- oder MemberRef-Token können im [IMetaDataImport-Objekt](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) für das entsprechende virtuelle ICorDebugModule-Objekt gesucht werden.|Gibt die IL im Assemblybild nach der Zusammenführung aus.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugProcess6-Schnittstelle](icordebugprocess6-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
