---
title: Ildasm.exe (IL Disassembler)
ms.date: 03/30/2017
helpviewer_keywords:
- PE files, MSIL Disassembler
- portable executable files, MSIL Disassembler
- Ildasm.exe
- MSIL Disassembler
- text files produced by MSIL Disassembler
- disassembling file for MSIL Assembler input
ms.assetid: db27f6b2-f1ec-499e-be3a-7eecf95ca42b
ms.openlocfilehash: f23f8c48a31dffa7d350c872aed7505da7a36861
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73105059"
---
# <a name="ildasmexe-il-disassembler"></a>Ildasm.exe (IL Disassembler)

Der IL-Disassembler ist ein ergänzendes Tool zum IL-Assembler (*Ilasm.exe*). *Ildasm.exe* erfasst eine portierbare ausführbare Datei (Portable Executable, PE) mit IL-Code (Intermediate Language) und erstellt eine Textdatei, die in *Ilasm.exe* eingegeben werden kann.

Dieses Tool wird automatisch mit Visual Studio installiert. Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).

Geben Sie an der Eingabeaufforderung Folgendes ein:

## <a name="syntax"></a>Syntax

```console
ildasm [options] [PEfilename] [options]
```

## <a name="parameters"></a>Parameter

Für Dateien mit den Erweiterungen *.exe*, *.dll*, *.obj*, *.lib* und *.winmd* stehen die folgenden Optionen zur Verfügung.

| Option | Beschreibung |
| ------ | ----------- |
|**/out=** `filename`|Erstellt eine Ausgabedatei mit dem angegebenen `filename`, anstatt die Ergebnisse in einer grafischen Benutzeroberfläche anzuzeigen.|
|**/rtf**|Erzeugt die Ausgabe im RTF-Format. Ungültig mit der Option **/text**.|
|**/text**|Zeigt die Ergebnisse nicht in einer grafischen Benutzeroberfläche oder einer Ausgabedatei an, sondern im Konsolenfenster.|
|**/html**|Erzeugt die Ausgabe im HTML-Format. Nur gültig mit der Option **/output**.|
|**/?**|Zeigt die Befehlssyntax und Optionen für das Tool an.|

Für Dateien mit den Erweiterungen *.exe*, *.dll* und *.winmd* stehen die folgenden zusätzlichen Optionen zur Verfügung.

| Option | Beschreibung |
| ------ | ----------- |
|**/bytes**|Zeigt die Bytes selbst im Hexadezimalformat als Kommentare zu Anweisungen an.|
|**/caverbal**|Erzeugt BLOBs des benutzerdefinierten Attributs im verbalen Format. Der Standard entspricht dem binären Format.|
|**/linenum**|Enthält Verweise auf die ursprünglichen Quellzeilen.|
|**/nobar**|Unterdrückt die Anzeige des Popupfensters mit der Statusanzeige für die Disassembly.|
|**/noca**|Unterdrückt die Ausgabe von benutzerdefinierten Attributen.|
|**/project**|Zeigt Metadaten so an, wie sie in verwalteten Code angezeigt werden, nicht wie in der nativen Windows-Runtime. Wenn `PEfilename` keine Windows-Metadatendatei ( *.winmd*) ist, hat diese Option keine Auswirkungen. Informationen finden Sie unter [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md).|
|**/pubonly**|Disassembliert ausschließlich öffentliche Typen und Member. Entspricht **/visibility:PUB**.|
|**/quoteallnames**|Schließt alle Namen in einfache Anführungszeichen ein.|
|**/raweh**|Zeigt Klauseln für die Ausnahmebehandlung in unformatierter Form an.|
|**/source**|Zeigt die ursprünglichen Quellzeilen als Kommentare an.|
|**/tokens**|Zeigt Metadatentoken von Klassen und Membern an.|
|**/visibility:** `vis`[+`vis`...]|Disassembliert nur Typen bzw. Member mit der angegebenen Sichtbarkeit. Die folgenden Werte sind für `vis` gültig:<br /><br /> **PUB** – Public<br /><br /> **PRI** – Private<br /><br /> **FAM** – Family<br /><br /> **ASM** – Assembly<br /><br /> **FAA** – Family und Assembly<br /><br /> **FOA** – Family oder Assembly<br /><br /> **PSC** – Private Scope<br /><br /> Definitionen dieser Sichtbarkeitsmodifizierer finden Sie unter <xref:System.Reflection.MethodAttributes> und <xref:System.Reflection.TypeAttributes>.|

Die folgenden Optionen gelten nur für Dateien mit den Erweiterungen *.exe*, *.dll* und *.winmd* bei der Ausgabe in einer Datei oder der Konsole.

| Option | Beschreibung |
| ------ | ----------- |
|**/all**|Gibt eine Kombination der Optionen **/header**, **/bytes**, **/stats**, **/classlist** und **/tokens** an.|
|**/classlist**|Umfasst eine Liste der im Modul definierten Klassen.|
|**/forward**|Verwendet die Vorwärtsklassendeklaration.|
|**/headers**|Schließt Informationen über den Dateiheader in der Ausgabe ein.|
|**/item:** `class`[ **::** `member`[`(sig`]]|Disassembliert Folgendes in Abhängigkeit vom angegebenen Argument:<br /><br /> – Disassembliert die angegebene `class`.<br />– Disassembliert den angegebenen `member` der `class`.<br />– Disassembliert den `member` der `class` mit der angegebenen Signatur `sig`. Das Format von `sig` lautet wie folgt:<br />     [`instance`] `returnType`(`parameterType1`, `parameterType2`, …, `parameterTypeN`)<br />     **Hinweis:** In .NET Framework, Versionen 1.0 und 1.1, muss auf `sig` eine schließende Klammer folgen: `(sig)`. Ab .NET Framework 2.0 muss die schließende Klammer weggelassen werden: `(sig`.|
|**/noil**|Unterdrückt die Ausgabe von IL-Assemblycode.|
|**/stats**|Schließt Statistiken zum Abbild ein.|
|**/typelist**|Erzeugt die vollständige Liste mit Typen, um die Reihenfolge von Typen bei Roundtrips beizubehalten.|
|**/unicode**|Verwendet Unicode-Codierung für die Ausgabe.|
|**/utf8**|Verwendet UTF-8-Codierung für die Ausgabe. ANSI ist die Standardeinstellung.|

Die folgenden Optionen gelten nur für Dateien mit den Erweiterungen *.exe*, *.dll*, *.obj*, *.lib* und *.winmd* bei der Ausgabe in einer Datei oder der Konsole.

| Option | Beschreibung |
| ------ | ----------- |
|**/metadata**[=`specifier`]|Zeigt Metadaten an. Dabei entspricht `specifier` Folgendem:<br /><br /> **MDHEADER**: Zeigt die Headerinformationen und -größen der Metadaten an.<br /><br /> **HEX**: Zeigt Informationen im Hexadezimalformat sowie in Wörtern an.<br /><br /> **CSV**: Zeigt die Anzahl von Datensätzen und die Heapgrößen an.<br /><br /> **UNREX**: Zeigt nicht aufgelöste Externe an.<br /><br /> **SCHEMA**: Zeigt den Metadatenheader und Schemainformationen an.<br /><br /> **RAW**: Zeigt die nicht formatierten Metadatentabellen an.<br /><br /> **HEAPS**: zeigt die unformatierten Heaps an.<br /><br /> **VALIDATE**: Überprüft die Konsistenz der Metadaten.<br /><br /> Sie können **/metadata** mehrmals angeben und unterschiedliche Werte für `specifier` verwenden.|

Die folgenden Optionen gelten nur für *LIB*-Dateien bei der Ausgabe in eine Datei oder auf der Konsole.

| Option | Beschreibung |
| ------ | ----------- |
|**/objectfile**=`filename`|Zeigt die Metadaten einer einzelnen Objektdatei in der angegebenen Bibliothek an.|

> [!NOTE]
> Bei allen Optionen für *Ildasm.exe* wird nicht zwischen Groß- und Kleinschreibung unterschieden, und sie werden anhand der ersten drei Buchstaben erkannt. **/quo** entspricht beispielsweise **/quoteallnames**. Optionen, die Argumente angeben, können entweder einen Doppelpunkt (:) oder ein Gleichheitszeichen (=) als Trennzeichen zwischen der Option und dem Argument enthalten. Beispiel: **/output:** *filename* entspricht **/output=** *filename*.

## <a name="remarks"></a>Hinweise

*Ildasm.exe* funktioniert nur bei PE-Dateien auf der Festplatte. Bei Dateien, die im globalen Assemblycache installiert sind, funktioniert dieses Tool nicht.

Die von *Ildasm.exe* erstellte Textdatei kann als Eingabe für den IL-Assembler (*Ilasm.exe*) verwendet werden. Dies ist zum Beispiel nützlich, wenn Code in einer Programmiersprache programmiert werde soll, die nicht alle Attribute der Metadaten der Laufzeit unterstützt. Nachdem der Code kompiliert und seine Ausgabe über *Ilasm.exe* verarbeitet wurde, kann die resultierende IL-Textdatei manuell bearbeitet werden, um die fehlenden Attribute hinzuzufügen. Sie können diese Textdatei anschließend durch den IL-Assembler ausführen, um eine endgültige ausführbare Datei zu erstellen.

> [!NOTE]
> Für PE-Dateien, die eingebetteten systemeigenen Code enthalten (z. B. von Visual C++ erstellte PE-Dateien), ist dieses Verfahren gegenwärtig jedoch nicht geeignet.  

In der als Standard festgelegten grafischen Benutzeroberfläche des IL-Disassemblers können Sie sich die Metadaten und den disassemblierten Code aller vorhandenen PE-Dateien als hierarchische Struktur anzeigen lassen. Geben Sie zum Aufrufen der Benutzeroberfläche an der Befehlszeile **ildasm** ein, ohne dabei das *PEfilename*-Argument oder Optionen anzugeben. Im Menü **Datei** können Sie zu der PE-Datei navigieren, die Sie in *Ildasm.exe* laden möchten. Um die Metadaten und den disassemblierten Code zu speichern, die für die ausgewählte PE angezeigt werden, wählen Sie im Menü **Datei** den Befehl **Sichern** aus. Wenn Sie nur die angezeigte hierarchische Struktur speichern möchten, wählen Sie im Menü **Datei** den Befehl **Strukturansicht sichern** aus. Ausführliche Anleitungen zum Laden einer Datei in *Ildasm.exe* und zum Interpretieren der Ausgabe finden Sie im Tutorial für *Ildasm.exe*. Dies ist im Lieferumfang des Windows SDK enthalten und befindet sich im Ordner „Samples“.

Wenn Sie *Ildasm.exe* mit dem *PEfilename*-Argument angeben, das eingebettete Ressourcen enthält, erstellt das Tool mehrere Ausgabedateien: eine Textdatei mit IL-Code und für jede eingebettete verwaltete Ressource eine RESOURCES-Datei, die unter Verwendung des Ressourcennamens aus Metadaten erstellt wird. Wenn in *PEfilename* eine nicht verwaltete Ressource eingebettet ist, wird eine RES-Datei unter Verwendung des Dateinamens erstellt, der durch die Option **/output** für die IL-Ausgabe angegeben wird.

> [!NOTE]
> *Ildasm.exe* zeigt für Eingabedateien mit den Erweiterungen *.obj* und *.lib* nur Metadatenbeschreibungen an. Für diese Dateitypen wird IL-Code nicht disassembliert.

Sie können *Ildasm.exe* für eine EXE- oder *DLL*-Datei ausführen, um festzustellen, ob die Datei verwaltet ist. Wenn die Datei nicht verwaltet ist, zeigt das Tool eine Meldung an, dass die Datei keinen gültigen Common Language Runtime-Header enthält und nicht disassembliert werden kann. Bei einer verwalteten Datei wird das Tool erfolgreich ausgeführt.

## <a name="version-information"></a>Versionsinformationen

Ab .NET Framework 4.5 verarbeitet *Ildasm.exe* ein unbekanntes Marshall-BLOB (Binary Large Object), indem der unformatierte binäre Inhalt angezeigt wird. Beispielsweise wird im folgenden Code veranschaulicht, wie ein BLOB-Marshall, der von einem C#-Programm generiert wird, angezeigt wird:

```csharp
public void Test([MarshalAs((short)70)] int test) { }
```

```il
// IL from Ildasm.exe output
.method public hidebysig instance void Test(int32  marshal({ 46 }) test) cil managed
```

Ab .NET Framework 4.5 zeigt *Ildasm.exe* Attribute an, die auf Schnittstellenimplementierungen angewendet werden, wie im folgenden Auszug der Ausgabe von *Ildasm.exe* zu sehen:

```il
.class public auto ansi beforefieldinit MyClass
  extends [mscorlib]System.Object
  implements IMyInterface
  {
    .interfaceimpl type IMyInterface
    .custom instance void
      [mscorlib]System.Diagnostics.DebuggerNonUserCodeAttribute::.ctor() = ( 01 00 00 00 )
      …
```

## <a name="examples"></a>Beispiele

Mit dem folgenden Befehl werden die Metadaten und der disassemblierte Code für die PE-Datei `MyHello.exe` in der als Standard festgelegten grafischen Benutzeroberfläche von *Ildasm.exe* angezeigt.

```console
ildasm myHello.exe
```

Der folgende Befehl disassembliert die Datei `MyFile.exe` und speichert den erstellten IL-Assembler-Text in der Datei *MyFile.il*.

```console
ildasm MyFile.exe /output:MyFile.il
```

Der folgende Befehl disassembliert die Datei `MyFile.exe` und zeigt den erstellten IL-Assembler-Text im Konsolenfenster an.

```console
ildasm MyFile.exe /text
```

Wenn die Datei `MyApp.exe` eingebettete verwaltete und nicht verwaltete Ressourcen enthält, erstellt der folgende Befehl diese vier Dateien: *MyApp.il*, *MyApp.res*, *Icons.resources* und *Message.resources*:

```console
ildasm MyApp.exe /output:MyApp.il
```

Der folgende Befehl disassembliert die `MyMethod`-Methode in der `MyClass`-Klasse in `MyFile.exe`und zeigt die Ausgabe im Konsolenfenster an.

```console
ildasm /item:MyClass::MyMethod MyFile.exe /text
```

Im vorigen Beispiel waren mehrere Methoden mit dem Namen `MyMethod` mit unterschiedlichen Signaturen möglich. Der folgende Befehl disassembliert die `MyMethod`-Instanzmethode mit dem Rückgabetyp **void** und den Parametertypen **int32** und **string**.

```console
ildasm /item:"MyClass::MyMethod(instance void(int32,string)" MyFile.exe /text
```

> [!NOTE]
> In den .NET Framework-Versionen 1.0 und 1.1 muss die öffnende Klammer, die auf den Methodennamen folgt, durch eine schließende Klammer hinter der Signatur ergänzt werden: `MyMethod(instance void(int32))`. Ab .NET Framework 2.0 muss die schließende Klammer weggelassen werden: `MyMethod(instance void(int32)`.

Um eine `static`-Methode (`Shared`-Methode in Visual Basic) abzurufen, lassen Sie das Schlüsselwort `instance` weg. Klassentypen, die keine Typen sind, beispielsweise `int32` und `string`, müssen den Namespace enthalten, und ihnen muss das Schlüsselwort `class` vorangestellt sein. Externen Typen muss der Bibliotheksname in eckigen Klammern vorangestellt werden. Der folgende Befehl disassembliert eine statische Methode namens `MyMethod`, die einen Parameter vom Typ <xref:System.AppDomain> und den Rückgabetyp <xref:System.AppDomain> besitzt.

```console
ildasm /item:"MyClass::MyMethod(class [mscorlib]System.AppDomain(class [mscorlib]System.AppDomain)" MyFile.exe /text
```

Bei einem geschachtelten Typ muss die Klasse, in der er enthalten ist, vorangestellt sein, begrenzt von einem Schrägstrich. Wenn die `MyNamespace.MyClass`-Klasse z. B. eine geschachtelte Klasse mit dem Namen `NestedClass` enthält, wird die geschachtelte Klasse folgendermaßen identifiziert: `class MyNamespace.MyClass/NestedClass`.

## <a name="see-also"></a>Siehe auch

- [Extras](index.md)
- [Ilasm.exe (IL-Assembler)](ilasm-exe-il-assembler.md)
- [Der verwaltete Ausführungsprozess](../../standard/managed-execution-process.md)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
