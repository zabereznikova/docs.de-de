---
title: Technologiebeispiel für einfache Serialisierung
ms.date: 03/30/2017
ms.assetid: 9d824e16-08d1-4a36-bc7f-2388c1f75f34
ms.openlocfilehash: e5dcc9ec7cf6f996c97262b14020552286c530da
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353140"
---
# <a name="basic-serialization-technology-sample"></a>Technologiebeispiel für einfache Serialisierung

[Beispiel herunterladen](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/Basic.zip.exe)

Dieses Beispiel zeigt, wie die Common Language Runtime ein Objektdiagramm im Speicher in einen Datenstream serialisieren kann. In diesem Beispiel kann entweder <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> oder <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> für die Serialisierung verwendet werden. Eine mit Daten gefüllte verknüpfte Liste wird in einen Dateistream serialisiert bzw. aus diesem deserialisiert. In beiden Fällen wird die Liste mit den Ergebnissen angezeigt. Die verknüpfte Liste ist vom Typ `LinkedList`, einem durch dieses Beispiel definierten Typ.

Weitere Informationen zur Serialisierung finden Sie in den Kommentaren der Quellcodedateien und der Datei "build.proj".

### <a name="to-build-the-sample-using-the-command-prompt"></a>So erstellen Sie das Beispiel mithilfe der Eingabeaufforderung

1. Navigieren Sie mithilfe der Eingabeaufforderung zu einem der sprachspezifischen Unterverzeichnisse unter dem Verzeichnis "Technologies\Serialization\Runtime Serialization\Basic".

2. Geben Sie je nach verwendeter Programmiersprache **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** oder **msbuild SerializationVB.sln** in der Befehlszeile ein.

### <a name="to-build-the-sample-using-visual-studio"></a>So erstellen Sie das Beispiel mithilfe von Visual Studio

1. Öffnen Sie den Datei-Explorer, und navigieren Sie zu einem der sprachspezifischen Unterverzeichnisse für das Beispiel.

2. Doppelklicken Sie je nach verwendeter Programmiersprache auf das Symbol für die Datei SerializationCS.sln, SerializationJSL.sln oder SerializationVB.sln, um die Datei in Visual Studio zu öffnen.

3. Wählen Sie im Menü **Erstellen** die Option **Projektmappe erstellen** aus.

 Die Beispielanwendung wird im Standardunterverzeichnis \bin oder \bin\Debug erstellt.

### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus

1. Navigieren Sie zu dem Verzeichnis, das die erstellte ausführbare Datei enthält.

2. Geben Sie **Serialization.exe** zusammen mit den gewünschten Parameterwerten in der Befehlszeile ein.

  > [!NOTE]
  > In diesem Beispiel wird eine Konsolenanwendung erstellt. Sie müssen es über die Eingabeaufforderung starten, um die Ausgabe anzuzeigen.

## <a name="remarks"></a>Hinweise

Die Beispielanwendung akzeptiert Befehlszeilenparameter, die angeben, welcher Test durchgeführt werden soll. Verwenden Sie die **sx Test.xml 10**-Parameter, um eine Liste mit 10 Knoten mithilfe der SOAP-Formatierung in eine Datei mit dem Namen **Test.xml** zu serialisieren.

Beispiel:

```console
Serialize.exe -sx Test.xml 10
```

Verwenden Sie die **dx Test.xml**-Parameter, um die Datei **Test.xml** aus dem vorherigen Beispiel zu deserialisieren.

Beispiel:

```console
Serialize.exe -dx Test.xml
```

In den beiden oben aufgeführten Beispielen bedeutet das "x" im Befehlszeilenschalter, dass die XML-SOAP-Serialisierung durchgeführt werden soll. Verwenden Sie "b", um die binäre Serialisierung durchzuführen. Wenn die Serialisierung mit einer großen Anzahl an Knoten durchgeführt werden soll, sollten Sie die Konsolenausgabe in eine Datei umleiten.

Beispiel:

```console
Serialize.exe -sb Test.bin 10000 >somefile.txt
```

In der folgenden Aufzählung werden die in diesem Beispiel verwendeten Klassen und Technologien kurz beschrieben.

- Laufzeitserialisierung

  - <xref:System.Runtime.Serialization.IFormatter> Wird verwendet, um auf ein <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Objekt oder ein <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>-Objekt zu verweisen.

  - <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Wird verwendet, um eine verknüpfte Liste in einen Stream in einem binären Format zu serialisieren. Die Binärformatierung verwendet ein Format, das nur der <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Typ versteht. Die Daten sind jedoch präzise.

  - <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Wird verwendet, um eine verknüpfte Liste in einen Stream im SOAP-Format zu serialisieren. SOAP ist ein Standardformat.

- Stream-E/A

  - <xref:System.IO.Stream> Wird zum Serialisieren und Deserialisieren verwendet. Bei dem in diesem Beispiel verwendeten speziellen Streamtyp handelt es sich um den <xref:System.IO.FileStream>-Typ. Die Serialisierung kann jedoch mit einem beliebigen aus <xref:System.IO.Stream> abgeleitetet Typ durchgeführt werden.

  - <xref:System.IO.File> Wird zum Erstellen von <xref:System.IO.FileStream>-Objekten zum Lesen und Erstellen von Dateien auf einem Datenträger verwendet.

  - <xref:System.IO.FileStream> Wird zum Serialisieren und Deserialisieren verknüpfter Listen verwendet.

## <a name="see-also"></a>Siehe auch

- <xref:System.IO>
- <xref:System.IO.File>
- <xref:System.IO.FileStream>
- <xref:System.IO.Stream>
- <xref:System.Random>
- <xref:System.Runtime.Serialization>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
- <xref:System.Runtime.Serialization.IFormatter>
- <xref:System.SerializableAttribute>
- <xref:System.Xml.Serialization>
- [Einfache Serialisierung](../../../docs/standard/serialization/basic-serialization.md)
- [Binäre Serialisierung](../../../docs/standard/serialization/binary-serialization.md)
- [Steuern der XML-Serialisierung mit Attributen](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)
- [Einführung in die XML-Serialisierung](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [Serialisierung](../../../docs/standard/serialization/index.md)
- [XML- und SOAP-Serialisierung](../../../docs/standard/serialization/xml-and-soap-serialization.md)
