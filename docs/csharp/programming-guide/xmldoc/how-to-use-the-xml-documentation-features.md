---
title: Verwenden der XML-Dokumentationsfeatures – C#-Programmierhandbuch
ms.date: 06/01/2018
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: b7c5a8a895271f067505496c0d13f98b66a393d9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287362"
---
# <a name="how-to-use-the-xml-documentation-features"></a>Verwenden der XML-Dokumentationsfeatures

Das folgende Beispiel bietet eine grundlegende Übersicht über einen Typ, der dokumentiert wurde.

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideDocComments#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#15)]

Im Beispiel wird eine *XML*-Datei mit dem folgenden Inhalt generiert.

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xmlsample</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            <summary>
            Class level summary documentation goes here.
            </summary>
            <remarks>
            Longer comments can be associated with a type or member through
            the remarks tag.
            </remarks>
        </member>
        <member name="F:TestClass._name">
            <summary>
            Store for the Name property.
            </summary>
        </member>
        <member name="M:TestClass.#ctor">
            <summary>
            The class constructor.
            </summary>
        </member>
        <member name="P:TestClass.Name">
            <summary>
            Name property.
            </summary>
            <value>
            A value tag is used to describe the property value.
            </value>
        </member>
        <member name="M:TestClass.SomeMethod(System.String)">
            <summary>
            Description for SomeMethod.
            </summary>
            <param name="s"> Parameter description for s goes here.</param>
            <seealso cref="T:System.String">
            You can use the cref attribute on any tag to reference a type or member
            and the compiler will check that the reference exists.
            </seealso>
        </member>
        <member name="M:TestClass.SomeOtherMethod">
            <summary>
            Some other method.
            </summary>
            <returns>
            Return values are described through the returns tag.
            </returns>
            <seealso cref="M:TestClass.SomeMethod(System.String)">
            Notice the use of the cref attribute to reference a specific method.
            </seealso>
        </member>
        <member name="M:TestClass.Main(System.String[])">
            <summary>
            The entry point for the application.
            </summary>
            <param name="args"> A list of command line arguments.</param>
        </member>
        <member name="T:TestInterface">
            <summary>
            Documentation that describes the interface goes here.
            </summary>
            <remarks>
            Details about the interface go here.
            </remarks>
        </member>
        <member name="M:TestInterface.InterfaceMethod(System.Int32)">
            <summary>
            Documentation that describes the method goes here.
            </summary>
            <param name="n">
            Parameter n requires an integer argument.
            </param>
            <returns>
            The method returns an integer.
            </returns>
        </member>
    </members>
</doc>
```

## <a name="compiling-the-code"></a>Kompilieren des Codes

Geben Sie den folgenden Befehl ein, um das Beispiel zu kompilieren:

`csc XMLsample.cs /doc:XMLsample.xml`

Mit diesem Befehl wird die XML-Datei *XMLsample.xml* erstellt, die Sie in Ihrem Browser oder mithilfe des `TYPE`-Befehls anzeigen können.

## <a name="robust-programming"></a>Stabile Programmierung

Die XML-Dokumentation beginnt mit `///`. Wenn Sie ein neues Projekt erstellen, fügt der Assistent einige `///`-Startzeilen für Sie ein. Die Verarbeitung dieser Kommentare weist einige Einschränkungen auf:

- Die Dokumentation muss wohlgeformtes XML sein. Wenn das XML nicht wohlgeformt ist, wird eine Warnung generiert, und die Dokumentationsdatei enthält einen Kommentar, der besagt, dass ein Fehler aufgetreten ist.

- Entwickler können ihren eigenen Satz von Tags erstellen. Es gibt einen [empfohlenen Satz von Tags](recommended-tags-for-documentation-comments.md). Einige der empfohlenen Tags haben eine besondere Bedeutung:

  - Das `<param>`-Tag wird verwendet, um Parameter zu beschreiben. Wenn es verwendet wird, überprüft der Compiler, ob der Parameter vorhanden ist, und ob alle Parameter in der Dokumentation beschrieben werden. Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.

  - Das `cref`-Attribut kann an jedes Tag angefügt werden, um auf ein Codeelement zu verweisen. Der Compiler überprüft, ob dieses Codeelement vorhanden ist. Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus. Der Compiler berücksichtigt alle `using`-Anweisungen, wenn er nach einem Typ sucht, der im `cref`-Attribut beschrieben wird.

  - Das `<summary>`-Tag wird von IntelliSense in Visual Studio verwendet, um zusätzliche Informationen über einen Typ oder Member anzuzeigen.

    > [!NOTE]
    > Die XML-Datei enthält keine vollständigen Informationen über den Typ und die Member (z. B. fehlen Typinformationen). Verwenden Sie die Dokumentationsdatei zusammen mit Reflektion über den tatsächlichen Typ oder Member, um vollständige Informationen zu einem Typ oder Member zu erhalten.

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [-doc (C#-Compileroptionen)](../../language-reference/compiler-options/doc-compiler-option.md)
- [XML-Dokumentationskommentare](./index.md)
- [DocFX-Dokumentationsprozessor](https://dotnet.github.io/docfx/)
- [Sandcastle-Dokumentationsprozessor](https://github.com/EWSoftware/SHFB)
