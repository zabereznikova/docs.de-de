---
title: <useLegacyJit>-Element
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a467599084f01b1a48c95c5e25fb1f869156dffa
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278758"
---
# <a name="uselegacyjit-element"></a>\<UseLegacyJit >-Element

Legt fest, ob die Runtime den 64-Bit-JIT-Legacycompiler für die Just-in-Time-Kompilierung verwendet.  
  
\<configuration>  
\<runtime>  
\<useLegacyJit>
  
## <a name="syntax"></a>Syntax  
  
```xml
<useLegacyJit enabled=0|1 />
```

Der Elementname `useLegacyJit` Groß-/Kleinschreibung beachtet wird.
  
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
| Attribut | Beschreibung                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | Erforderliches Attribut.<br><br>Gibt an, ob die Runtime die älteren 64-Bit-JIT-Compiler verwendet. |  
  
### <a name="enabled-attribute"></a>Enabled-Attribut  
  
| Wert | Beschreibung                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| 0     | Die common Language Runtime verwendet, den neuen 64-Bit-JIT-Compiler in der .NET Framework 4.6 und höheren Versionen enthalten. |  
| 1     | Die common Language Runtime verwendet die älteren 64-Bit-JIT-Compiler.                                                     |  
  
### <a name="child-elements"></a>Untergeordnete Elemente

Keine
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
| Element         | Beschreibung                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |  
| `runtime`       | Enthält Informationen über Laufzeitinitialisierungsoptionen.                                                        |  
  
## <a name="remarks"></a>Hinweise  

Ab .NET Framework 4.6, verwendet die common Language Runtime einen neuen 64-Bit-Compiler für Just-in-Time (JIT)-Kompilierung standardmäßig möglich werden. In einigen Fällen kann dies einen Unterschied im Verhalten von Anwendungscode führen, die von der vorherigen Version des 64-Bit-JIT-Compilers JIT-kompiliert wurde. Durch Festlegen der `enabled` Attribut der `<useLegacyJit>` Element `1`, können Sie den neuen 64-Bit-JIT-Compiler zu deaktivieren und stattdessen Ihre app mit dem älteren 64-Bit-JIT-Compiler zu kompilieren.  
  
> [!NOTE]
> Die `<useLegacyJit>` Element betrifft nur 64-Bit-JIT-Kompilierung. Kompilierung mit der 32-Bit-JIT-Compiler ist nicht betroffen.  
  
Anstatt eine Konfigurationseinstellung für die Datei zu verwenden, können Sie den älteren 64-Bit-JIT-Compiler auf zwei weitere Arten aktivieren:  
  
- Festlegen von Umgebungsvariablen

  Legen Sie die `COMPLUS_useLegacyJit` Umgebungsvariable entweder `0` (verwenden Sie den neuen 64-Bit-JIT-Compiler) oder `1` (verwenden Sie die älteren 64-Bit-JIT-Compiler):
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  Die Umgebungsvariable hat *globalen Gültigkeitsbereich*, d. h., die sie wirkt sich auf alle Anwendungen auf dem Computer ausgeführt. Wenn festgelegt, es durch eine Einstellung der Anwendung Konfigurationsdatei überschrieben werden kann. Der Name der Umgebungsvariablen ist nicht in der Groß-/Kleinschreibung beachtet.
  
- Hinzufügen eines Registrierungsschlüssels

  Sie können die älteren 64-Bit-JIT-Compiler aktivieren, durch das Hinzufügen einer `REG_DWORD` Wert, der entweder die `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` oder `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` -Schlüssel in der Registrierung. Der Wert wird als `useLegacyJit`. Wenn der Wert 0 ist, wird der neue Compiler verwendet. Wenn der Wert 1 ist, ist der ältere 64-Bit-JIT-Compiler aktiviert. Der Name des Registrierungsschlüssels wird nicht beachtet.
  
  Hinzufügen des Werts, der die `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` Schlüssel wirkt sich auf alle apps, die auf dem Computer ausgeführt. Hinzufügen des Werts, der die `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` Schlüssel wirkt sich auf alle apps, die vom aktuellen Benutzer ausgeführt. Wenn ein Computer mit mehreren Benutzerkonten konfiguriert ist, sind nur apps, die vom aktuellen Benutzer ausgeführt betroffen, es sei denn, die Registrierungsschlüssel für andere Benutzer als auch der Wert hinzugefügt wird. Hinzufügen der `<useLegacyJit>` Elements zu einer Konfigurationsdatei überschreibt die registrierungseinstellungen aus, wenn sie vorhanden sind.  
  
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

- [\<Common Language Runtime >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [\<configuration> Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
- [Entschärfung: Neue 64-Bit-JIT-Compiler](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)
