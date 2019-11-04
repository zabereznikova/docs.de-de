---
title: Ilasm.exe (IL-Assembler)
ms.date: 03/30/2017
helpviewer_keywords:
- MSIL generators
- metadata, MSIL Assembler
- MSIL Assembler
- portable executable files, MSIL Assembler
- PE files, MSIL Assembler
- MSIL
- Ilasm.exe
- verifying MSIL performance
ms.assetid: 4ca3a4f0-4400-47ce-8936-8e219961c76f
ms.openlocfilehash: cb995e78e534048043886070536ef0dd0a45c057
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105095"
---
# <a name="ilasmexe-il-assembler"></a>Ilasm.exe (IL-Assembler)

Der IL-Assembler generiert eine portierbare ausführbare Datei (Portable Executable, PE) aus der Zwischensprache (Intermediate Language, IL). Weitere Informationen über die Zwischensprache finden Sie unter [Der verwaltete Ausführungsprozess](../../standard/managed-execution-process.md). Die erstellte ausführbare Datei, die IL und die erforderlichen Metadaten enthält, können Sie ausführen, um zu überprüfen, ob die IL wie erwartet funktioniert.

Dieses Tool wird automatisch mit Visual Studio installiert. Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).

Geben Sie an der Eingabeaufforderung Folgendes ein:

## <a name="syntax"></a>Syntax

```console
ilasm [options] filename [[options]filename...]
```

## <a name="parameters"></a>Parameter

| Argument | BESCHREIBUNG |
| -------- | ----------- |
|`filename`|Der Name der IL-Quelldatei. Diese Datei besteht aus Direktiven für die Deklaration von Metadaten und symbolischen IL-Anweisungen. Zum Erstellen einer einzelnen PE-Datei mithilfe von *Ilasm.exe* können mehrere Quelldateiargumente angegeben werden. **Hinweis**: Vergewissern Sie sich, dass die letzte Codezeile in der IL-Quelldatei entweder ein nachgestelltes Leerzeichen oder ein Zeilenendezeichen besitzt.|

| Option | BESCHREIBUNG |
| ------ | ----------- |
|**/32bitpreferred**|Erstellt ein Abbild im PE32-Format (vorzugweise 32 Bit).|
|**/alignment:** `integer`|Legt FileAlignment auf den Wert fest, der im NT Optional-Header per `integer` angegeben ist. Wenn die .alignment-IL-Direktive in der Datei angegeben ist, wird sie durch diese Option überschrieben.|
|**/appcontainer**|Erstellt als Ausgabe eine *DLL*- oder *EXE*-Datei, die im Windows-App-Container ausgeführt wird.|
|**/arm**|Gibt die ARM (Advanced RISC Machine) als Zielprozessor an.<br /><br /> Wenn keine Bitanzahl für das Abbild angegeben wird, lautet der Standardwert **/32bitpreferred**.|
|**/base:** `integer`|Legt ImageBase auf den Wert fest, der im NT Optional-Header per `integer` angegeben ist. Wenn die .imagebase-IL-Direktive in der Datei angegeben ist, wird sie durch diese Option überschrieben.|
|**/clock**|Erfasst und berichtet die folgenden Kompilierungszeiten (in Millisekunden) für die angegebene IL-Quelldatei:<br /><br /> **Total Run:** Die gesamte für die Ausführung aller nachfolgenden spezifischen Vorgänge benötigte Zeit.<br /><br /> **Startup:** Laden und Öffnen der Datei.<br /><br /> **Emitting MD:** Ausgabe von Metadaten.<br /><br /> **Ref to Def Resolution:** Auflösen von Verweisen auf Definitionen in der Datei.<br /><br /> **CEE File Generation:** Generieren des Dateiimages im Arbeitsspeicher.<br /><br /> **PE File Writing:** Schreiben des Images in eine PE-Datei.|
|**/debug**[:**IMPL**&#124;**OPT**]|Schließt Debuginformationen (Namen lokaler Variablen und Argumente sowie Zeilennummern) ein. Erstellt eine PDB-Datei.<br /><br /> **/debug** ohne zusätzlichen Wert deaktiviert die JIT-Optimierung und verwendet Sequenzpunkte aus der PDB-Datei.<br /><br /> **IMPL** deaktiviert die JIT-Optimierung und verwendet implizite Sequenzpunkte.<br /><br /> **OPT** aktiviert die JIT-Optimierung und verwendet implizite Sequenzpunkte.|
|**/dll**|Erzeugt eine *DLL*-Datei als Ausgabe.|
|**/enc:** `file`|Erstellt Edit-and-Continue-Deltas aus der angegebenen Quelldatei.<br /><br /> Die Verwendung dieses Arguments ist nur zu akademischen Zwecken vorgesehen. Ein Einsatz zu kommerziellen Zwecken wird nicht unterstützt.|
|**/exe**|Erstellt eine ausführbare Datei als Ausgabe. Dies ist die Standardeinstellung.|
|**/flags:** `integer`|Legt ImageFlags“ auf den Wert, der im Common Language Runtime-Header durch `integer` angegeben wird. Wenn die .corflags-IL-Direktive in der Datei angegeben ist, wird sie durch diese Option überschrieben. Eine Liste der für *integer*gültigen Werte finden Sie unter "CorHdr.h, COMIMAGE_FLAGS".|
|**/fold**|Fasst identische Methodentexte in einem Text zusammen.|
|/**highentropyva**|Erstellt eine ausführbare Ausgabedatei, die ASLR mit hoher Entropie (Address Space Layout Randomization, Zufällige Anordnung des Layouts des Adressraums) unterstützt. (Standardeinstellung für **/appcontainer**.)|
|**/include:** `includePath`|Legt einen Suchpfad für in `#include`aufgeführte Dateien fest.|
|**/itanium**|Gibt Intel Itanium als Zielprozessor an.<br /><br /> Wenn keine Bitanzahl für das Abbild angegeben wird, lautet der Standardwert **/pe64**.|
|**/key:** `keyFile`|Kompiliert `filename` mit einer starken Signatur unter Verwendung des privaten Schlüssels in `keyFile`.|
|**/key:**  @`keySource`|Kompiliert `filename` mit einer starken Signatur unter Verwendung des bei `keySource` erstellten privaten Schlüssels.|
|**/listing**|Erstellt eine Listingdatei in der Standardausgabe. Wenn Sie diese Option weglassen, wird keine Listingdatei erstellt.<br /><br /> In .NET Framework 2.0 (oder höher) wird dieser Parameter nicht unterstützt.|
|**/mdv:** `versionString`|Legt die Zeichenfolge der Metadatenversion fest.|
|**/msv:** `major`.`minor`|Legt die Version des Metadatenstreams fest, wobei `major` und `minor` ganze Zahlen sind.|
|**/noautoinherit**|Deaktiviert die Standardvererbung von <xref:System.Object> , wenn keine Basisklasse angegeben ist.|
|**/nocorstub**|Unterdrückt die Generierung des CORExeMain-Stubs.|
|**/nologo**|Unterdrückt die Anzeige des Startbanners von Microsoft.|
|**/output:** `file.ext`|Gibt den Namen und die Erweiterung der Ausgabedatei an. In der Standardeinstellung ist der Name der Ausgabedatei mit dem der ersten Quelldatei identisch. Die Standarderweiterung ist *.exe*. Wenn Sie die Option **/dll** angeben, lautet die Standarderweiterung *.dll*. **Hinweis**: Durch Angabe von „ **/output**:myfile.dll“ wird die Option **/dll** nicht festgelegt. Wenn Sie **/dll** nicht angeben, wird eine ausführbare Datei mit dem Namen *myfile.dll* erstellt.|
|**/optimize**|Optimiert lange Anweisungen in kurze Anweisungen. Beispiel: `br` wird zu `br.s`.|
|**/pe64**|Erstellt ein 64-Bit-Abbild (PE32+).<br /><br /> Wenn kein Zielprozessor angegeben wird, lautet der Standardwert `/itanium`.|
|**/pdb**|Erstellt eine PDB-Datei, ohne das Nachverfolgen von Debuginformationen zu aktivieren.|
|**/quiet**|Gibt den stillen Modus an, bei dem keine Angaben zum Verlauf der Assembly gemeldet werden.|
|**/resource:** `file.res`|Bezieht die angegebene Ressourcendatei im Format „\*.res“ in die resultierende *EXE*- oder *DLL*-Datei ein. Mit der Option **/resource** kann nur eine einzige RES-Datei angegeben werden.|
|**/ssver:** `int`.`int`|Legt die Subsystemversionsnummer im NT Optional-Header fest. Für **/appcontainer** und **/arm** lautet die minimale Versionsnummer 6.02.|
|**/stack:** `stackSize`|Legt den SizeOfStackReserve-Wert im NT Optional-Header auf `stackSize`fest.|
|**/stripreloc**|Gibt an, dass Basisumsetzungen nicht erforderlich sind.|
|**/subsystem:** `integer`|Legt „subsystem“ auf den Wert fest, der im NT Optional-Header durch `integer` angegeben wird. Wenn die .subsystem-IL-Direktive in der Datei angegeben ist, wird sie durch diesen Befehl überschrieben. Eine Liste der gültigen Werte für `integer` finden Sie unter „winnt.h, IMAGE_SUBSYSTEM“.|
|**/x64**|Gibt einen 64-Bit-AMD-Prozessor als Zielprozessor an.<br /><br /> Wenn keine Bitanzahl für das Abbild angegeben wird, lautet der Standardwert **/pe64**.|
|**/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|

> [!NOTE]
> Bei allen Optionen für *Ilasm.exe* wird nicht zwischen Groß- und Kleinschreibung unterschieden, und sie werden anhand der ersten drei Buchstaben erkannt. So ist zum Beispiel **/lis** das Gleiche wie **/listing**, und **/res**:myresfile.res entspricht **/resource:** myresfile.res. Optionen, die Argumente angeben, können entweder einen Doppelpunkt (:) oder ein Gleichheitszeichen (=) als Trennzeichen zwischen der Option und dem Argument enthalten. So wären zum Beispiel **/output:** *file.ext* und **/output=** =*file.ext* identisch.

## <a name="remarks"></a>Anmerkungen

Der IL-Assembler unterstützt Anbieter von Tools beim Entwerfen und Implementieren von IL-Generatoren. Durch die Verwendung von *Ilasm.exe* können sich Entwickler von Tools und Compilern auf die Generierung von IL und Metadaten konzentrieren, ohne sich um IL-Ausgaben im PE-Dateiformat kümmern zu müssen.

Ähnlich wie andere Laufzeitcompiler (z.B. C# und Visual Basic) erstellt *Ilasm.exe* keine Objektzwischendateien und benötigt keine Verknüpfungsstufe zum Erstellen einer PE-Datei.

Der IL-Assembler kann alle vorhandenen Metadaten und IL-Funktionen der Programmiersprachen ausdrücken, die die Laufzeit unterstützen. Dadurch kann verwalteter Code, der in einer dieser Programmiersprachen geschrieben wurde, im IL-Assembler adäquat ausgedrückt und mit *Ilasm.exe* kompiliert werden.

> [!NOTE]
> Wenn die letzte Codezeile in der IL-Quelldatei weder ein nachgestelltes Leerzeichen noch ein Zeilenendezeichen besitzt, kann die Kompilierung fehlschlagen.

Sie können *Ilasm.exe* zusammen mit dem zugehörigen Tool [*Ildasm.exe*](ildasm-exe-il-disassembler.md) verwenden. *Ildasm.exe* nimmt eine PE-Datei mit IL-Code entgegen und erstellt eine Textdatei, die als Eingabe für *Ilasm.exe* geeignet ist. Dies ist zum Beispiel nützlich, wenn Code in einer Programmiersprache programmiert werde soll, die nicht alle Attribute der Metadaten der Laufzeit unterstützt. Nachdem der Code kompiliert und die Ausgabe über *Ildasm.exe* verarbeitet wurde, kann die resultierende IL-Textdatei manuell bearbeitet werden, um die fehlenden Attribute hinzuzufügen. Anschließend können Sie diese Textdatei per *Ilasm.exe* verarbeiten, um eine endgültige ausführbare Datei zu erstellen.

Mit diesem Verfahren können Sie auch eine einzelne PE-Datei aus mehreren PE-Dateien erstellen, die von unterschiedlichen Compilern generiert wurden.

> [!NOTE]
> Für PE-Dateien, die eingebetteten systemeigenen Code enthalten (z. B. von Visual C++ erstellte PE-Dateien), ist dieses Verfahren gegenwärtig jedoch nicht geeignet.

Damit dieses Zusammenspiel von *Ildasm.exe* und *Ilasm.exe* so exakt wie möglich erfolgt, ersetzt der Assembler lange Codierungen (die Sie möglicherweise in Ihren IL-Quellen geschrieben haben oder die aus einem anderen Compiler ausgegeben wurden) standardmäßig nicht durch kurze Codierungen. Verwenden Sie die Option **/optimize** , um kurze Codierungen nach Möglichkeit zu ersetzen.

> [!NOTE]
> *Ildasm.exe* kann nur für Dateien auf der Festplatte verwendet werden. Bei Dateien, die im globalen Assemblycache installiert sind, funktioniert dieses Tool nicht.

Weitere Informationen zur Grammatik von IL finden Sie in der Datei „asmparse.grammar“ im Windows SDK.

## <a name="version-information"></a>Versionsinformationen

Ab .NET Framework 4.5 können Sie ein benutzerdefiniertes Attribut an eine Schnittstellenimplementierung anfügen, indem Sie Code verwenden, der in etwa wie folgt aussieht:

```il
.class interface public abstract auto ansi IMyInterface
{
  .method public hidebysig newslot abstract virtual
    instance int32 method1() cil managed
  {
  } // end of method IMyInterface::method1
} // end of class IMyInterface
.class public auto ansi beforefieldinit MyClass
  extends [mscorlib]System.Object
  implements IMyInterface
  {
    .interfaceimpl type IMyInterface
    .custom instance void
      [mscorlib]System.Diagnostics.DebuggerNonUserCodeAttribute::.ctor() = ( 01 00 00 00 )
      …
```

Ab .NET Framework 4.5 können Sie ein beliebiges Marshall-BLOB (Binary Large Object) angeben, indem Sie die entsprechenden unformatierten Binärdaten wie im folgenden Code gezeigt angeben:

```il
.method public hidebysig abstract virtual
        instance void
        marshal({ 38 01 02 FF })
        Test(object A_1) cil managed
```

Weitere Informationen zur Grammatik von IL finden Sie in der Datei „asmparse.grammar“ im Windows SDK.

## <a name="examples"></a>Beispiele

Der folgende Befehl assembliert die IL-Datei *myTestFile.il* und erstellt die ausführbare Datei *myTestFile.exe*.

```console
ilasm myTestFile
```

Der folgende Befehl assembliert die IL-Datei *myTestFile.il* und erstellt die *DLL*-Datei *myTestFile.dll*.

```console
ilasm myTestFile /dll
```

Der folgende Befehl assembliert die IL-Datei *myTestFile.il* und erstellt die *DLL*-Datei *myNewTestFile.dll*.

```console
ilasm myTestFile /dll /output:myNewTestFile.dll
```

Im folgenden Codebeispiel wird eine sehr einfache Anwendung gezeigt, die "Hello World!" auf der Konsole aus. Sie können diesen Code kompilieren und dann das Tool [*Ildasm.exe*](ildasm-exe-il-disassembler.md) verwenden, um eine IL-Datei zu generieren.

```csharp
using System;

public class Hello
{
    public static void Main(String[] args)
    {
        Console.WriteLine("Hello World!");
    }
}
```

Das folgende IL-Codebeispiel entspricht dem vorherigen C#-Codebeispiel. Sie können diesen Code mithilfe des IL Assembler-Tools in eine Assembly kompilieren. Sowohl der IL- als auch der C#-Beispielcode geben "Hello World!" auf der Konsole aus.

```il
// Metadata version: v2.0.50215
.assembly extern mscorlib
{
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..
  .ver 2:0:0:0
}
.assembly sample
{
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )
  .hash algorithm 0x00008004
  .ver 0:0:0:0
}
.module sample.exe
// MVID: {A224F460-A049-4A03-9E71-80A36DBBBCD3}
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    //  ILONLY
// Image base: 0x02F20000

// =============== CLASS MEMBERS DECLARATION ===================

.class public auto ansi beforefieldinit Hello
       extends [mscorlib]System.Object
{
  .method public hidebysig static void  Main(string[] args) cil managed
  {
    .entrypoint
    // Code size       13 (0xd)
    .maxstack  8
    IL_0000:  nop
    IL_0001:  ldstr      "Hello World!"
    IL_0006:  call       void [mscorlib]System.Console::WriteLine(string)
    IL_000b:  nop
    IL_000c:  ret
  } // end of method Hello::Main

  .method public hidebysig specialname rtspecialname
          instance void  .ctor() cil managed
  {
    // Code size       7 (0x7)
    .maxstack  8
    IL_0000:  ldarg.0
    IL_0001:  call       instance void [mscorlib]System.Object::.ctor()
    IL_0006:  ret
  } // end of method Hello::.ctor

} // end of class Hello
```

## <a name="see-also"></a>Siehe auch

- [Extras](index.md)
- [*Ildasm.exe* (IL-Disassembler)](ildasm-exe-il-disassembler.md)
- [Der verwaltete Ausführungsprozess](../../standard/managed-execution-process.md)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
