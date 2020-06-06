---
title: <useLegacyJit>-Element
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
ms.openlocfilehash: a126b8c0050a8d1fd96a3d090f9b018a9faa07a7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968857"
---
# <a name="uselegacyjit-element"></a>\<useLegacyJit>-Element

Legt fest, ob die Runtime den 64-Bit-JIT-Legacycompiler für die Just-in-Time-Kompilierung verwendet.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<useLegacyJit>**  
  
## <a name="syntax"></a>Syntax  
  
```xml
<useLegacyJit enabled=0|1 />
```

Beim Elementnamen `useLegacyJit` wird die Groß-/Kleinschreibung beachtet.
  
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
| attribute | BESCHREIBUNG                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | Erforderliches Attribut.<br><br>Gibt an, ob die Laufzeit den Legacy-JIT-Compiler mit 64-Bit verwendet. |  
  
### <a name="enabled-attribute"></a>aktiviertes Attribut  
  
| Wert | BESCHREIBUNG                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| 0     | Der Common Language Runtime verwendet den neuen 64-Bit-JIT-Compiler, der in der .NET Framework 4,6 und höheren Versionen enthalten ist. |  
| 1     | Der Common Language Runtime verwendet den älteren JIT-Compiler von 64 Bit.                                                     |  
  
### <a name="child-elements"></a>Untergeordnete Elemente

Keine
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
| Element         | Beschreibung                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |  
| `runtime`       | Enthält Informationen über Laufzeitinitialisierungsoptionen.                                                        |  
  
## <a name="remarks"></a>Bemerkungen  

Beginnend mit dem .NET Framework 4,6 verwendet die Common Language Runtime standardmäßig einen neuen 64-Bit-Compiler für die Just-in-time (JIT)-Kompilierung. In einigen Fällen kann dies zu einem Unterschied im Verhalten von Anwendungscode führen, der von der vorherigen Version des JIT-Compilers der 64-Bit-Version JIT-kompiliert wurde. Indem Sie das- `enabled` Attribut des- `<useLegacyJit>` Elements auf festlegen `1` , können Sie den neuen 64-Bit-JIT-Compiler deaktivieren und stattdessen die App mithilfe des Legacy-JIT-Compilers (64-Bit) kompilieren.  
  
> [!NOTE]
> Das `<useLegacyJit>` Element wirkt sich nur auf die JIT-Kompilierung 64-Bit aus Die Kompilierung mit dem 32-Bit-JIT-Compiler ist nicht betroffen.  
  
Anstatt eine Konfigurationsdatei Einstellung zu verwenden, können Sie den Legacy-JIT-Compiler von 64 auf zwei weitere Arten aktivieren:  
  
- Festlegen einer Umgebungsvariablen

  Legen `COMPLUS_useLegacyJit` Sie die Umgebungsvariable entweder auf `0` (verwenden Sie den neuen 64-Bit-JIT-Compiler) oder `1` (verwenden Sie den älteren 64-Bit-JIT-Compiler):
  
  ```env  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  Die Umgebungsvariable verfügt über einen globalen Gültigkeits *Bereich*. Dies bedeutet, dass Sie sich auf alle auf dem Computer durchgeführten Anwendungen auswirkt. Wenn diese Einstellung festgelegt ist, kann Sie von der Einstellung für die Anwendungs Konfigurationsdatei überschrieben werden. Beim Namen der Umgebungsvariablen muss die Groß-/Kleinschreibung nicht beachtet werden.
  
- Hinzufügen eines Registrierungsschlüssels

  Sie können den Legacy-JIT-Compiler von 64 aktivieren, indem Sie `REG_DWORD` dem-oder- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` Schlüssel in der Registrierung einen-Wert hinzufügen. Der Wert hat den Namen `useLegacyJit` . Wenn der Wert 0 ist, wird der neue Compiler verwendet. Wenn der Wert 1 ist, ist der ältere 64-Bit-JIT-Compiler aktiviert. Beim Namen des Registrierungswerts wird die Groß-/Kleinschreibung nicht beachtet.
  
  Das Hinzufügen des Werts zum `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` Schlüssel betrifft alle apps, die auf dem Computer ausgeführt werden. Das Hinzufügen des Werts zum `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` Schlüssel wirkt sich auf alle apps aus, die vom aktuellen Benutzer ausgeführt werden. Wenn ein Computer mit mehreren Benutzerkonten konfiguriert ist, wirkt sich dies nur auf apps aus, die vom aktuellen Benutzer ausgeführt werden, es sei denn, der Wert wird den Registrierungs Schlüsseln für andere Benutzer ebenfalls hinzugefügt. Das Hinzufügen des- `<useLegacyJit>` Elements zu einer Konfigurationsdatei überschreibt die Registrierungs Einstellungen, sofern diese vorhanden sind.  
  
## <a name="example"></a>Beispiel  

Die folgende Konfigurationsdatei deaktiviert die Kompilierung mit dem neuen 64-Bit-JIT-Compiler und verwendet stattdessen den älteren 64-Bit-JIT-Compiler.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [\<runtime>Gewisses](runtime-element.md)
- [\<configuration>Gewisses](../configuration-element.md)
- [Entschärfung: Neuer 64-Bit-JIT-Compiler](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)
