---
title: '&lt;UseLegacyJit&gt; Element'
ms.custom: 
ms.date: 04/26/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9d2a71e44db2d6e85ae730f4603bf191f54525c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltuselegacyjitgt-element"></a>&lt;UseLegacyJit&gt; Element

Legt fest, ob die Runtime den 64-Bit-JIT-Legacycompiler für die Just-in-Time-Kompilierung verwendet.  
  
\<configuration>  
\<Common Language Runtime >  
\<UseLegacyJit >
  
## <a name="syntax"></a>Syntax  
  
```xml
<useLegacyJit enabled=0|1 />
```

Der Elementname `useLegacyJit` Groß-/Kleinschreibung beachtet.
  
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
| Attribut | Beschreibung                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | Erforderliches Attribut.<br><br>Gibt an, ob die Laufzeit den älteren 64-Bit-JIT-Compiler verwendet. |  
  
### <a name="enabled-attribute"></a>Enabled-Attribut  
  
| Wert | Beschreibung                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| 0     | Die common Language Runtime verwendet den neue 64-Bit-JIT-Compiler in der .NET Framework 4.6 und höher enthalten. |  
| 1     | Die common Language Runtime verwendet die älteren 64-Bit-JIT-Compiler.                                                     |  
  
### <a name="child-elements"></a>Untergeordnete Elemente

Keiner
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
| Element         | Beschreibung                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |  
| `runtime`       | Enthält Informationen über Laufzeitinitialisierungsoptionen.                                                        |  
  
## <a name="remarks"></a>Hinweise  

Beginnend mit .NET Framework 4.6, verwendet die common Language Runtime einen neuen 64-Bit-Compiler für Just-in-Time (JIT)-Kompilierung standardmäßig möglich werden. In einigen Fällen kann dies einen Unterschied im Verhalten von Anwendungscode haben, die von der vorherigen Version des 64-Bit-JIT-Compilers JIT-kompiliert wurde. Durch Festlegen der `enabled` Attribut von der `<useLegacyJit>` Element `1`, Sie können den neue 64-Bit-JIT-Compiler deaktivieren und stattdessen Ihre app mit der älteren 64-Bit-JIT-Compiler kompilieren.  
  
> [!NOTE]
> Die `<useLegacyJit>` Element betrifft nur 64-Bit-JIT-Kompilierung. Kompilierung mit der 32-Bit-JIT-Compiler ist nicht betroffen.  
  
Anstatt Einstellung einer Konfigurationsdatei zu verwenden, können Sie die älteren 64-Bit-JIT-Compiler auf zwei andere Arten aktivieren:  
  
- Eine Umgebungsvariable festlegen

  Legen Sie die `COMPLUS_useLegacyJit` Umgebungsvariable entweder `0` (verwenden Sie die neuen 64-Bit-JIT-Compiler) oder `1` (verwenden Sie die älteren 64-Bit-JIT-Compiler):
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  Die Umgebungsvariable weist *globalen Gültigkeitsbereich*, d. h., die sie wirkt sich auf alle Anwendungen auf dem Computer ausgeführt. Wenn festgelegt, es von der Anwendung der Konfigurationseinstellung überschrieben werden kann. Der Umgebungsvariablenname ist nicht in der Groß-/Kleinschreibung beachtet.
  
- Hinzufügen eines Registrierungsschlüssels

  Sie können die älteren 64-Bit-JIT-Compiler durch Hinzufügen von eine `REG_DWORD` Wert entweder die `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` oder `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` Schlüssel in der Registrierung. Der Wert lautet `useLegacyJit`. Wenn der Wert 0 ist, wird der neue Compiler verwendet. Wenn der Wert 1 ist, wird der ältere 64-Bit-JIT-Compiler aktiviert. Der Name des Registrierungsschlüssels ist nicht in der Groß-/Kleinschreibung beachtet.
  
  Hinzufügen den Wert, der die `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` Schlüssel wirkt sich auf alle apps, die auf dem Computer ausgeführt. Hinzufügen den Wert, der die `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` Schlüssel wirkt sich auf alle apps, die vom aktuellen Benutzer ausgeführt. Wenn ein Computer mit mehreren Benutzerkonten konfiguriert ist, werden nur apps, die vom aktuellen Benutzer ausgeführt beeinflusst, wenn die Registrierungsschlüssel für andere Benutzer als auch der Wert hinzugefügt wird. Hinzufügen der `<useLegacyJit>` Element zu einer Konfigurationsdatei überschreibt die registrierungseinstellungen, wenn sie vorhanden sind.  
  
## <a name="example"></a>Beispiel  

Die folgende Konfigurationsdatei deaktiviert die Kompilierung mit dem neuen 64-Bit-JIT-Compiler und verwendet stattdessen die älteren 64-Bit-JIT-Compiler.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

[\<Common Language Runtime >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)   
[\<Konfiguration >-Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)   
[Entschärfung: Neuer 64-Bit-JIT-Compiler](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)
