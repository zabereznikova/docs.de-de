---
ms.openlocfilehash: 0237c848d71150aaea1f9de4f4b16a0cbbc4ab3a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615666"
---
### <a name="new-64-bit-jit-compiler-in-the-net-framework-46"></a>Neuer 64-Bit-JIT-Compiler in .NET Framework 4.6

#### <a name="details"></a>Details

Ab .NET Framework 4.6 wird ein neuer 64-Bit-JIT-Compiler für die Just-in-Time-Kompilierung verwendet. In einigen Fällen wird eine unerwartete Ausnahme ausgelöst oder ein anderes Verhalten beobachtet als bei der Ausführung des 32-Bit-Compilers oder des älteren 64-Bit-JIT-Compilers. Diese Änderung wirkt sich nicht auf den 32-Bit-JIT-Compiler aus. Die bekannten Unterschiede umfassen folgende Punkte:

- Unter bestimmten Umständen kann ein Unboxingvorgang in Releasebuilds mit aktivierter Optimierung eine <xref:System.NullReferenceException>-Ausnahme auslösen.
- In manchen Fällen kann bei der Ausführung von Produktionscode in einem großen Methodentext eine <xref:System.StackOverflowException>-Ausnahme ausgelöst werden.
- Unter bestimmten Bedingungen werden in Releasebuilds an eine Methode übergebene Strukturen als Verweistypen statt als Werttypen behandelt. Eins der Anzeichen dieses Problems besteht darin, dass die einzelnen Elemente einer Sammlung in unerwarteter Reihenfolge angezeigt werden.
- Unter bestimmten Bedingungen ist der Vergleich von <xref:System.UInt16>-Werten mit festgelegtem hohem Bit fehlerhaft, wenn Optimierung aktiviert ist.
- Unter bestimmten Umständen, insbesondere beim Initialisieren von Arraywerten, kann die Speicherinitialisierung durch die IL-Anweisung <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> mit einem falschen Wert erfolgen. Dies kann entweder zu einem Ausnahmefehler oder zu einer falschen Ausgabe führen.
- Unter bestimmten seltenen Bedingungen kann ein bedingter Bittest den falschen <xref:System.Boolean>-Wert zurückgeben oder eine Ausnahme auslösen, wenn Compileroptimierungen aktiviert sind.
- Wenn unter bestimmten Umständen eine `if`-Anweisung für die Prüfung auf eine Bedingung vor dem Eintritt in einen `try`-Block oder beim Verlassen eines `try`-Blocks erfolgt und die gleiche Bedingung im `catch`- oder `finally`-Block ausgewertet wird, entfernt der neue 64-Bit-JIT-Compiler beim Optimieren von Code die `if`-Bedingung aus dem `catch`- oder `finally`-Block. Daher wird Code innerhalb der `if`-Anweisung im `catch`- oder `finally`-Block ohne Bedingung ausgeführt.

#### <a name="suggestion"></a>Vorschlag

**Entschärfung bekannter Probleme** <br/> Wenn bei Ihnen die oben aufgeführten Probleme auftreten, können Sie darauf mit einer der folgenden Maßnahmen reagieren:

- Ausführen eines Upgrades auf .NET Framework 4.6.2. Der neue 64-Bit-Compiler, der in .NET Framework 4.6.2 enthalten ist, behebt jedes dieser bekannten Probleme.
- Stellen Sie sicher, dass ihre Windows-Version auf dem aktuellen Stand ist, indem Sie Windows Update ausführen. Serviceupdates für .NET Framework 4.6 und 4.6.1 beheben jedes dieser Probleme, mit Ausnahme der <xref:System.NullReferenceException>-Ausnahme bei Unboxingvorgängen.
- Kompilieren Sie mit dem älteren 64-Bit-JIT-Compiler. Informationen zum Vorgehen dazu finden Sie unter **Entschärfung anderer Probleme**.
**Entschärfung anderer Probleme** <br/> Wenn Sie andere Unterschiede im Verhalten zwischen Code, der mit dem älteren 64-Bit-Compiler kompiliert wurde, gegenüber mit dem neuen 64-Bit-JIT-Compiler kompiliertem Code oder zwischen den Debug- und Releaseversionen Ihrer App feststellen, die beide mit dem neuen 64-Bit-JIT-Compiler kompiliert wurden, können Sie folgendermaßen vorgehen, um Ihre App mit dem älteren 64-Bit-JIT-Compiler zu kompilieren:

- Sie können der Konfigurationsdatei Ihrer Anwendung auf Anwendungsbasis das [<](~/docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md)-Element hinzufügen. Die folgende Anweisung deaktiviert die Kompilierung mit dem neuen 64-Bit-JIT-Compiler und verwendet stattdessen den 64-Bit-Legacy-JIT-Compiler.

    ```xml
    <?xml version ="1.0"?>
    <configuration>
      <runtime>
       <useLegacyJit enabled="1" />
      </runtime>
    </configuration>
    ```

- Auf Benutzerbasis können Sie dem `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`-Wert der Registrierung einen `REG_DWORD`-Wert mit dem Namen `useLegacyJit` hinzufügen. Der Wert 1 aktiviert den 64-Bit-Legacy-JIT-Compiler, der Wert 0 deaktiviert ihn und aktiviert stattdessen den neuen 64-Bit-JIT-Compiler.
- Auf Computerbasis können Sie dem `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`-Schlüssel der Registrierung einen `REG_DWORD`-Wert mit dem Namen `useLegacyJit` hinzufügen. Der Wert `1` aktiviert den 64-Bit-Legacy-JIT-Compiler, der Wert `0` deaktiviert ihn und aktiviert stattdessen den neuen 64-Bit-JIT-Compiler.
Ferner können Sie uns über das Problem informieren, indem Sie einen Bug auf [Microsoft Connect](https://connect.microsoft.com/VisualStudio) melden.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.6         |
| Typ    | Neuzuweisung |
