---
title: 'Gewusst wie: Verwenden der XML-Dokumentationsfunktionen (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eb647a275a5cd5fac2316706591440d9792861b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a>Gewusst wie: Verwenden der XML-Dokumentationsfunktionen (C#-Programmierhandbuch)
Das folgende Beispiel bietet eine grundlegende Übersicht über einen Typ, der dokumentierten wurde.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  
  
 **// Diese XML-Datei wurde mit dem vorherigen Codebeispiel generiert.**  
**\<?xml version="1.0"?>**  
**\<doc>**  
 **\<assembly>**  
 **\<name>xmlsample\</name>**  
 **\</assembly>**  
 **\<members>**  
 **\<member name="T:SomeClass">**  
 **\<summary>**  
 **Hier eine Zusammenfassung der Klassenebene dokumentieren.\</summary>**  
 **\<remarks>**  
 **Längere Kommentare können einen Typ oder Member zugeordnet werden.**  
 **Kommentare zugeordnet werden.\</remarks>**  
 **\</member>**  
 **\<member name="F:SomeClass.m_Name">**  
 **\<summary>**  
 **Speicher für die Name-Eigenschaft\</summary>**  
 **\</member>**  
 **\<member name="M:SomeClass.#ctor">**  
 **\<Zusammenfassung > Klassenkonstruktor.  \< /summary >**  
 **\</member>**  
 **\<member name="M:SomeClass.SomeMethod(System.String)">**  
 **\<summary>**  
 **Beschreibung von SomeMethod.\</summary>**  
 **\<param name="s">Hier Beschreibung für den Parameter „s“ einfügen.\</param>**  
 **\<seealso cref="T:System.String">**  
 **Sie können auf einem beliebigen Tag Cref-Attribut verwenden, auf einen Typ oder Member verweisen**  
 **zu verweisen. Der Compiler prüft dann, ob der Verweis vorhanden ist. \</seealso>**  
 **\</member>**  
 **\<member name="M:SomeClass.SomeOtherMethod">**  
 **\<summary>**  
 **Eine andere Methode. \</summary>**  
 **\<returns>**  
 **Rückgabeergebnisse werden mit returns-Tags beschrieben.\</returns>**  
 **\<seealso cref="M:SomeClass.SomeMethod(System.String)">**  
 **Beachten Sie die Verwendung des cref-Attributs, um auf eine bestimmte Methode zu verweisen.\</seealso>**  
 **\</member>**  
 **\<member name="M:SomeClass.Main(System.String[])">**  
 **\<summary>**  
 **Der Einstiegspunkt der Anwendung.**  
 **\</summary>**  
 **\<param name="args"> Eine Liste der Befehlszeilenargumente.\</param>**  
 **\</member>**  
 **\<member name="P:SomeClass.Name">**  
 **\<summary>**  
 **Name-Eigenschaft \</summary>**  
 **\<value>**  
 **Der Eigenschaftswert wird mit value-Tags beschrieben.\</value>**  
 **\</member>**  
 **\</members>**  
**\</doc>**   
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Geben Sie die folgende Befehlszeile ein, um das Beispiel zu kompilieren:  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 Dadurch wird die XML-Datei „XMLsample.xml“ erstellt, die Sie in Ihrem Browser oder mithilfe des TYPE-Befehls anzeigen können.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 XML-Dokumentation beginnt mit ///. Wenn Sie ein neues Projekt erstellen, fügt der Assistent einige ///-Startzeilen für Sie ein. Die Verarbeitung dieser Kommentare weist einige Einschränkungen auf:  
  
-   Die Dokumentation muss wohlgeformtes XML sein. Wenn das XML nicht wohlgeformt ist, wird eine Warnung generiert, und die Dokumentationsdatei enthält einen Kommentar, der besagt, dass ein Fehler aufgetreten ist.  
  
-   Entwickler können ihren eigenen Satz von Tags erstellen. Es gibt ein Reihe empfohlener Tags (siehe Abschnitt „Weiterführende Themen“). Einige der empfohlenen Tags haben eine besondere Bedeutung:  
  
    -   Das \<param>-Tag wird verwendet, um Parameter zu beschreiben. Wenn es verwendet wird, überprüft der Compiler, ob der Parameter vorhanden ist und dass alle Parameter in der Dokumentation beschrieben werden. Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.  
  
    -   Das `cref`-Attribut kann an jedes Tag angefügt werden, um einen Verweis auf ein Codeelement bereitzustellen. Der Compiler überprüft, ob dieses Codeelement vorhanden ist. Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus. Der Compiler berücksichtigt alle `using`-Anweisungen, wenn er nach einem Typ sucht, der im `cref`-Attribut beschrieben wird.  
  
    -   Das \<summary>-Tag wird von IntelliSense in Visual Studio verwendet, um zusätzliche Informationen über einen Typ oder Member anzuzeigen.  
  
        > [!NOTE]
        >  Die XML-Datei enthält keine vollständigen Informationen über den Typ und die Member (z. B. fehlen Typinformationen). Um vollständige Informationen zu einem Typ oder Member zu erhalten, muss die Dokumentationsdatei zusammen mit Reflektion über den tatsächlichen Typ oder Member verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [/ doc (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [XML-Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
