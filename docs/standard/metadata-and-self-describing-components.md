---
title: Metadaten und selbstbeschreibende Komponenten
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- runtime, metadata
- languages, interoperability
- portable executable files, metadata
- self-describing files
- metadata, about metadata
- common language runtime, metadata
- PE files, metadata
- components [.NET], metadata
ms.assetid: 3dd13c5d-a508-455b-8dce-0a852882a5a7
ms.openlocfilehash: 2ed09882ba722ace0b7f7be2a35fffc362af2742
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159351"
---
# <a name="metadata-and-self-describing-components"></a>Metadaten und selbstbeschreibende Komponenten

Früher konnte eine in einer bestimmten Sprache geschriebene Softwarekomponente (.exe oder .dll) nicht einfach eine andere Softwarekomponente verwenden, die in einer anderen Sprache geschrieben war. COM ist die Lösung dieses Problems angegangen. .NET erleichtert die Interoperation von Komponenten, indem zusätzliche deklarative Informationen von Compilern an alle Module und Assemblys weitergegeben werden. Diese Informationen, so genannte Metadaten, ermöglichen eine nahtlose Interaktion der Komponenten.

 Metadaten sind binäre Informationen, die ein Programm beschreiben, das entweder im Speicher oder in einer PE (Portable Executable)-Datei von Common Language Runtime gespeichert ist. Wenn Sie Code in eine PE-Datei kompilieren, werden in einen Bereich der Datei Metadaten eingefügt, während der Code in MSIL (Microsoft Intermediate Language) konvertiert und in einen anderen Bereich der Datei eingefügt wird. Jeder Typ und jeder Member, auf den in einem Modul oder in einer Assembly verwiesen wird, wird mit Metadaten beschrieben. Beim Ausführen von Code lädt Common Language Runtime Metadaten in den Speicher und verweist darauf, um Informationen zu Codeklassen, Membern, Vererbung usw. zu finden.

 Metadaten beschreiben auf sprachneutrale Weise alle im Code definierten Typen und Member. In Metadaten werden folgende Informationen gespeichert:

- Beschreibung der Assembly

  - Identität (Name, Version, Kultur, öffentlicher Schlüssel).

  - Typen, die exportiert werden.

  - Andere Assemblys, von denen diese Assembly abhängt.

  - Sicherheitsberechtigungen, die zur Ausführung benötigt werden.

- Typenbeschreibung

  - Name, Sichtbarkeit, Basisklasse und implementierte Schnittstellen.

  - Member (Methoden, Felder, Eigenschaften, Ereignisse, geschachtelte Typen).

- Attribute

  - Zusätzliche beschreibende Elemente, die Änderungen an Typen und Membern vornehmen.

## <a name="benefits-of-metadata"></a>Vorteile von Metadaten

Metadaten ermöglichen ein einfacheres Programmierungsmodell und machen IDL (Interface Definition Language)-Dateien, Headerdateien oder andere externe Methoden zum Verweisen auf Komponenten überflüssig. Mit Metadaten können .NET-Sprachen unabhängig vom Entwickler und Benutzer automatisch auf sprachneutrale Weise beschrieben werden. Metadaten sind zudem mithilfe von Attributen erweiterbar. Sie bieten die folgenden wesentlichen Vorteile:

- Selbstbeschreibende Dateien

  Common Language Runtime-Module und Assemblys sind selbstbeschreibend. Die Metadaten eines Moduls enthalten alle zur Interaktion mit einem anderen Modul benötigten Informationen. Metadaten stellen automatisch die gleichen Funktionalitäten zur Verfügung, die IDL in COM bereitstellt. Auf diese Weise können Sie eine Datei sowohl für Definition als auch für Implementierung verwenden. Laufzeitmodule und Assemblys erfordern nicht einmal eine Registrierung beim Betriebssystem. Die von Common Language Runtime verwendeten Beschreibungen geben daher den tatsächlichen Code in der kompilierten Datei wieder. Dies erhöht die Zuverlässigkeit von Anwendungen.

- Sprachübergreifende Interoperabilität und einfacheres, komponentenbasiertes Design

  Metadaten stellen alle Informationen über kompilierten Code zur Verfügung, die für das Erben einer Klasse aus einer PE-Datei, die in einer anderen Sprache geschrieben wurde, benötigt werden. Sie können eine Instanz einer beliebigen Klasse erstellen, die in einer beliebigen verwalteten Sprache geschrieben wurde (jede Sprache, die Common Language Runtime anspricht), ohne auf explizites Marshallen oder die Verwendung von benutzerdefiniertem Interoperabilitätscode zurückgreifen zu müssen.

- Attribute

  Mit .NET können Sie bestimmte Arten von Metadaten (sogenannte Attribute) in der kompilierten Datei deklarieren. Attribute befinden sich überall in .NET und werden zur detaillierteren Steuerung des Programms zur Laufzeit verwendet. Außerdem können Sie mithilfe von benutzerdefinierten Attributen Ihre eigenen benutzerdefinierten Metadaten in .NET-Dateien ausgeben. Weitere Informationen finden Sie unter [Attribute](attributes/index.md).

## <a name="metadata-and-the-pe-file-structure"></a>Metadaten und die PE-Dateistruktur

Metadaten werden in einem Bereich einer .NET-PE-Datei (portierbare ausführbare Datei) gespeichert, während MSIL (Microsoft Intermediate Language) in einem anderen Bereich der PE-Datei gespeichert wird. Der Metadatenbereich der Datei enthält eine Reihe von Tabellen und Heapdatenstrukturen. Der MSIL-Bereich enthält MSIL und Metadatentokens, die auf den Metadatenbereich der PE-Datei verweisen. Möglicherweise werden Metadatentoken verwendet, wenn Sie Tools wie [MSIL Disassembler-Tool (Ildasm.exe)](../framework/tools/ildasm-exe-il-disassembler.md) verwenden, um z.B. die MSIL des Codes anzuzeigen.

### <a name="metadata-tables-and-heaps"></a>Metadatentabellen und -heaps

Jede Metadatentabelle beinhaltet Informationen über die Elemente Ihres Programms. Eine Metadatentabelle beschreibt zum Beispiel die Klassen des Codes, eine andere beschreibt die Felder usw. Falls der Code z. B. zehn Klassen besitzt, enthält die Klassentabelle zehn Zeilen, eine für jede Klasse. Metadatentabellen verweisen auf andere Tabellen und Heaps. Die Metadatentabelle für Klassen verweist z. B. auf die Tabelle für Methoden.

Zusätzlich speichern Metadaten Informationen in vier Heapstrukturen: Zeichenfolge, BLOB, Benutzerzeichenfolge und GUID. Alle Zeichenfolgen zum Benennen von Typen und Membern werden im Stringheap gespeichert. Eine Methodentabelle speichert den Namen einer bestimmten Methode nicht direkt, sondern verweist auf dem im Stringheap gespeicherten Namen einer Methode.

### <a name="metadata-tokens"></a>Metadatentokens

Jede Zeile einer Metadatentabelle wird im MSIL-Bereich einer PE-Datei durch ein Metadatentoken eindeutig identifiziert. Metadatentokens sind konzeptionell identisch mit in MSIL beibehaltenen Zeigern, die auf eine bestimmte Metadatentabelle verweisen.

Ein Metadatentoken ist eine Vier-Byte-Zahl. Das oberste Byte kennzeichnet die Metadatentabelle, auf die ein bestimmtes Token verweist (Methode, Typ usw.). Die restlichen drei Bytes geben die Zeile in der Metadatentabelle an, die dem beschriebenen Programmierelement entspricht. Wenn Sie eine Methode in C# definieren und in eine PE-Datei kompilieren, befindet sich möglicherweise folgendes Metadatentoken im MSIL-Bereich der PE-Datei:

`0x06000004`

Das oberste Byte (`0x06`) gibt an, dass es sich um ein **MethodDef**-Token handelt. Die unteren drei Bytes (`000004`) weisen die **Common Language Runtime** an, in der vierten Zeile der MethodDef-Tabelle nach Informationen zu suchen, welche die Methodendefinition beschreiben.

### <a name="metadata-within-a-pe-file"></a>Metadaten in einer PE-Datei

Beim Kompilieren eines Programms für Common Language Runtime wird es in eine PE-Datei konvertiert, die aus drei Teilen besteht. In der folgenden Tabelle werden die einzelnen Teile beschrieben.

|PE-Abschnitt|Inhalt des PE-Abschnitts|
|----------------|----------------------------|
|PE-Header|Index der Hauptabschnitte der PE-Datei und Adresse des Einstiegspunktes.<br /><br /> Common Language Runtime verwendet diese Informationen, um die Datei als PE-Datei zu identifizieren und festzulegen, wo die Ausführung beginnt, wenn das Programm in den Speicher geladen wird.|
|MSIL-Anweisungen|MSIL-Anweisungen (Microsoft Intermediate Language), aus denen der Code besteht. Viele MSIL-Anweisungen werden von Metadatentokens begleitet.|
|Metadaten|Metadatentabellen und Heaps. Dieser Abschnitt wird von Common Language Runtime verwendet, um Informationen über jeden Typ und jeden Member des Codes aufzuzeichnen. Dieser Abschnitt enthält auch benutzerdefinierte Attribute und Sicherheitsinformationen.|

## <a name="run-time-use-of-metadata"></a>Verwenden von Metadaten zur Laufzeit

Zum besseren Verständnis von Metadaten und ihrer Rolle in Common Language Runtime kann es hilfreich sein, ein einfaches Programm zu schreiben, das zeigt, wie Metadaten das Verhalten der Laufzeit beeinflussen. Folgendes Codebeispiel zeigt zwei Methoden innerhalb der Klasse `MyApp`. Die `Main`-Methode ist der Einstiegspunkt des Programms, während die `Add`-Methode einfach die Summe zweier Ganzzahlargumente zurückgibt.

```vb
Public Class MyApp
   Public Shared Sub Main()
      Dim ValueOne As Integer = 10
      Dim ValueTwo As Integer = 20
      Console.WriteLine("The Value is: {0}", Add(ValueOne, ValueTwo))
   End Sub

   Public Shared Function Add(One As Integer, Two As Integer) As Integer
      Return (One + Two)
   End Function
End Class
```

```csharp
using System;
public class MyApp
{
   public static int Main()
   {
      int ValueOne = 10;
      int ValueTwo = 20;
      Console.WriteLine("The Value is: {0}", Add(ValueOne, ValueTwo));
      return 0;
   }
   public static int Add(int One, int Two)
   {
      return (One + Two);
   }
}
```

Beim Ausführen des Codes lädt Common Language Runtime das Modul in den Speicher und fragt die Metadaten für diese Klasse ab. Nach dem Laden analysiert Common Language Runtime ausführlich den MSIL (Microsoft Intermediate Language)-Stream der Methode, um ihn in schnelle systemeigene Anweisungen zu konvertieren. Common Language Runtime verwendet einen JIT (Just-In-Time)-Compiler, um bei Bedarf jeweils für eine Methode die MSIL-Anweisungen in systemeigenen Maschinencode zu konvertieren.

Das folgende Beispiel zeigt einen Teil der MSIL, die aus der `Main`-Funktion des vorherigen Codes erstellt wurde. Sie können die MSIL und die Metadaten aus jeder .NET-Anwendung mithilfe des [MSIL Disassembler-Tools (Ildasm.exe)](../framework/tools/ildasm-exe-il-disassembler.md) anzeigen.

```console
.entrypoint
.maxstack  3
.locals ([0] int32 ValueOne,
         [1] int32 ValueTwo,
         [2] int32 V_2,
         [3] int32 V_3)
IL_0000:  ldc.i4.s   10
IL_0002:  stloc.0
IL_0003:  ldc.i4.s   20
IL_0005:  stloc.1
IL_0006:  ldstr      "The Value is: {0}"
IL_000b:  ldloc.0
IL_000c:  ldloc.1
IL_000d:  call int32 ConsoleApplication.MyApp::Add(int32,int32) /* 06000003 */
```

Der JIT-Compiler liest die MSIL der ganzen Methode, analysiert sie ausführlich und generiert effiziente, systemeigene Anweisungen für diese Methode. Bei `IL_000d` wird ein Metadatentoken für die `Add`-Methode (`/*` `06000003 */`) ermittelt. Die Runtime verwendet dieses Token, um die dritte Zeile der **MethodDef**-Tabelle abzufragen.

Folgende Tabelle zeigt einen Teil der **MethodDef**-Tabelle, welche die `Add`-Methode beschreibt und auf die das Metadatentoken verweist. Obwohl es in dieser Assembly auch andere Metadatentabellen gibt, die jeweils ihre eigenen, eindeutigen Werte besitzen, wird hier nur diese Tabelle erläutert.

|Zeile|RVA (Relative Virtuelle Adresse)|ImplFlags|Flags|name<br /><br /> (Zeigt auf Zeichenfolgenheap.)|Signatur (Zeigt auf BLOB-Heap.)|
|---------|--------------------------------------|---------------|-----------|-----------------------------------------|----------------------------------------|
|1|0x00002050|IL<br /><br /> Verwaltet|Public<br /><br /> ReuseSlot<br /><br /> SpecialName<br /><br /> RTSpecialName<br /><br /> .ctor|.ctor (constructor)||
|2|0x00002058|IL<br /><br /> Verwaltet|Public<br /><br /> Statisch<br /><br /> ReuseSlot|Main|Zeichenfolge|
|3|0x0000208c|IL<br /><br /> Verwaltet|Public<br /><br /> Statisch<br /><br /> ReuseSlot|Hinzufügen|int, int, int|

Jede Spalte der Tabelle enthält wichtige Informationen über Ihren Code. Über die **RVA**-Spalte kann die Runtime die Startspeicheradresse der MSIL berechnen, die diese Methode definiert. Die **ImplFlags**-Spalte und die **Flags**-Spalte enthalten Bitmasken, welche die Methode beschreiben (z.B., ob es sich um eine öffentliche oder eine private Methode handelt). Die **Name**-Spalte gibt den Namen der Methode aus dem String-Heap an. Die Spalte **Signatur** gibt die Definition der Signatur der Methode im BLOB-Heap an.

Die Runtime berechnet die gewünschte Offset-Adresse aus der **RVA**-Spalte in der dritten Zeile und gibt diese Adresse an den JIT-Compiler zurück, der anschließend zur neuen Adresse übergeht. Der JIT-Compiler fährt mit der Verarbeitung der MSIL an der neuen Adresse fort, bis er erneut auf ein Metadatentoken trifft und der Prozess wiederholt wird.

Mithilfe von Metadaten stehen Common Language Runtime alle Informationen zur Verfügung, die benötigt werden, um den Code zu laden und in systemeigene Maschinenanweisungen zu verarbeiten. Auf diese Weise bilden Metadaten selbstbeschreibende Dateien und ermöglichen zusammen mit dem allgemeinen Typsystem sprachübergreifende Vererbung.

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[Attribute](attributes/index.md)|Beschreibt, wie Attribute angewendet, benutzerdefinierte Attribute geschrieben und in Attributen gespeicherte Informationen abgerufen werden.|
