---
title: "Gewusst wie: Verwenden der XML-Dokumentationsfunktionen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "XML-Dokumentation [C#]"
  - "C#-Sprache, XML-Dokumentationsfeatures"
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Gewusst wie: Verwenden der XML-Dokumentationsfunktionen (C#-Programmierhandbuch)
Das folgende Beispiel bietet eine grundlegende Übersicht über einen Typ, der dokumentierten.  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  
  
 **Dieser XML-Datei wurde mit dem vorherigen Beispiel generiert.**  
**\<? Xml Version = "1.0"?>**  
**\< Doc>**  
 **\< Assembly>**  
 **\< Name>Xmlsample \< / name>**  
 **\< / Assembly>**  
 **\< Member>**  
 **\< Elementname = "T:SomeClass">**  
 **\< Zusammenfassung>**  
 **Zusammenfassung der Klassenebene dokumentieren geht hier. \< / summary>**  
 **\< Beschreibung>**  
 **-Tag können ein Typ oder Member zugeordnet werden.**   
 **Kommentare \< / Beschreibung>**  
 **\< / Member>**  
 **\< Member name="F:SomeClass.m_Name">**  
 **\< Zusammenfassung>**  
 **Speicher für die Namenseigenschaft \< / summary>**  
 **\< / Member>**  
 **\< Elementname = "M:SomeClass. #ctor">**  
 **\< summary>Klasse Konstruktor. \< / summary>**   
 **\< / Member>**  
 **\< Member name="M:SomeClass.SomeMethod(System.String)">**  
 **\< Zusammenfassung>**  
 **Beschreibung für SomeMethod. \< / summary>**  
 **\< Param Name = "s"> Parameter für s Beschreibung \< / Param>**  
 **\< Seealso cref="T:System.String">**  
 **Cref-Attribut können für alle Tags Sie einen Typ oder Member verweisen**   
 **und der Compiler überprüft, dass der Verweis vorhanden ist. \< / Seealso>**  
 **\< / Member>**  
 **\< Member name="M:SomeClass.SomeOtherMethod">**  
 **\< Zusammenfassung>**  
 **Eine andere Methode. \< / summary>**  
 **\< zurückgibt>**  
 **Zurückgeben der Ergebnisse werden beschrieben, über den Tag zurück. \< / returns>**  
 **\< Seealso cref="M:SomeClass.SomeMethod(System.String)">**  
 **Beachten Sie die Verwendung des Cref-Attribut zum Verweisen auf eine bestimmte Methode \< / Seealso>**  
 **\< / Member>**  
 **\< Member name="M:SomeClass.Main(System.String[])">**  
 **\< Zusammenfassung>**  
 **Der Einstiegspunkt für die Anwendung.**  
 **\< / summary>**  
 **\< Param Name = "Args"> eine Liste der Befehlszeilenargumente \< / Param>**  
 **\< / Member>**  
 **\< Member name="P:SomeClass.Name">**  
 **\< Zusammenfassung>**  
 **Name-Eigenschaft \< / summary>**  
 **\< Wert>**  
 **Value-Tag wird verwendet, um den Wert der Eigenschaft beschreiben \< / Wert>**  
 **\< / Member>**  
 **\< / Member>**  
**\< / Doc>**   
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Geben Sie zum Kompilieren des Beispiels die folgende Befehlszeile ein:  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 Dadurch wird die XML-Datei XMLsample.XML erstellt, erstellt, die Sie in Ihrem Browser oder mithilfe des TYPE-Befehls anzeigen können.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 XML-Dokumentation beginnt mit / / /. Wenn Sie ein neues Projekt erstellen, fügt der Assistent einige Starter / / / Linien in für Sie. Die Verarbeitung dieser Kommentare weist einige Einschränkungen auf:  
  
-   Die Dokumentation muss wohlgeformt sein XML. Wenn das XML nicht wohlgeformt ist, wird eine Warnung generiert, und die Dokumentationsdatei enthält einen Kommentar, der besagt, dass ein Fehler aufgetreten ist.  
  
-   Entwickler können ihre eigenen Satz von Tags zu erstellen. Es gibt ein Reihe empfohlener Tags (siehe Abschnitt "Weiterführende Literatur). Einige der empfohlenen Tags haben eine besondere Bedeutung:  
  
    -   Das \< Param> Tag wird verwendet, um Parameter zu beschreiben. Wenn verwendet, stellt der Compiler sicher, dass der Parameter vorhanden ist und dass alle Parameter in der Dokumentation beschrieben werden. Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus.  
  
    -   Die `cref` Attribut angefügt werden kann, um alle Tags, um einen Verweis auf ein Codeelement bereitzustellen. Der Compiler überprüft, dass dieses Codeelement vorhanden ist. Wenn die Überprüfung fehlschlägt, gibt der Compiler eine Warnung aus. Der Compiler berücksichtigt alle `using` Anweisungen für einen Typ, der in beschriebenen durchsucht die `cref` Attribut.  
  
    -   Das \< summary> -Tag wird von IntelliSense in Visual Studio verwendet, um zusätzliche Informationen über einen Typ oder Member anzuzeigen.  
  
        > [!NOTE]
        >  Die XML-Datei bietet keine vollständigen Informationen zu Typen und Membern (es ist z. B. keine Typinformationen). Um vollständige Informationen zu einem Typ oder Member zu erhalten, muss die Dokumentationsdatei zusammen mit Reflektion für den tatsächlichen Typ oder Member verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [/ doc (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [XML-Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)