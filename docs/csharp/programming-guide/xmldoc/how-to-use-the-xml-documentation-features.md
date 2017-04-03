---
title: 'Vorgehensweise: Verwenden der XML-Dokumentationsfunktionen (C#-Programmierhandbuch) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f4e74e2da4a5f8ba0a9964a5eff4f2a492b8981f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a>Gewusst wie: Verwenden der XML-Dokumentationsfunktionen (C#-Programmierhandbuch)
Das folgende Beispiel bietet eine grundlegende Übersicht über einen Typ, der dokumentierten wurde.  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  
  
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
 **Mit den remarks-Tags können einem Typ oder Member längere**   
 **Kommentare zugeordnet werden.\</remarks>**  
 **\</member>**  
 **\<member name="F:SomeClass.m_Name">**  
 **\<summary>**  
 **Speicher für die Name-Eigenschaft\</summary>**  
 **\</member>**  
 **\<member name="M:SomeClass.#ctor">**  
 **\<summary>Konstruktor der Klasse.\</summary>**   
 **\</member>**  
 **\<member name="M:SomeClass.SomeMethod(System.String)">**  
 **\<summary>**  
 **Beschreibung von SomeMethod.\</summary>**  
 **\<param name="s">Hier Beschreibung für den Parameter „s“ einfügen.\</param>**  
 **\<seealso cref="T:System.String">**  
 **Sie können für alle Tags das cref-Attribut verwenden, um auf einen Typ oder Member**   
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
 [/doc (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [XML-Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
