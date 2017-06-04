---
title: "Parameterentwurf | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Entwurfsrichtlinien für Member [.NET Framework], Parameter"
  - "[Member [.NET Framework], Parameter"
  - "[Namen [.NET Framework], Parameter"
  - "Entwurfsrichtlinien für Parameter"
  - "reservierte Parameter"
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Parameterentwurf
Dieser Abschnitt enthält allgemeine Richtlinien auf Parameter, einschließlich Abschnitte mit Richtlinien für das Überprüfen von Argumenten. Darüber hinaus finden Sie in den Richtlinien unter [Benennen von Parametern](../../../docs/standard/design-guidelines/naming-parameters.md).  
  
 **✓ führen** verwenden, der am wenigsten abgeleiteten Parametertyp, der die Funktionen für das Element bereitstellt.  
  
 Angenommen Sie, dass eine Methode entworfen wird, die listet und jedes Element in der Konsole ausgegeben, werden soll. Eine solche Methode ergreift <xref:System.Collections.IEnumerable> als Parameter nicht <xref:System.Collections.ArrayList> oder <xref:System.Collections.IList>, z. B..  
  
 **X nicht** reservierte Parameter verwenden.  
  
 Wenn weitere Eingaben auf einen Member in einer künftigen Version erforderlich ist, kann eine neue Überladung hinzugefügt werden.  
  
 **X nicht** haben öffentlich verfügbar gemachten Methoden, die Zeiger, Arrays von Zeigern oder mehrdimensionale Arrays als Parameter akzeptieren.  
  
 Zeiger und mehrdimensionale Arrays sind relativ schwierig ordnungsgemäß zu verwenden. In fast allen Fällen können APIs überarbeitet werden, um zu vermeiden, diese Typen als Parameter übernimmt.  
  
 **✓ führen** setzen Sie alle `out` Parameter, die alle den Wert und `ref` Parameter \(ausgenommen Parameterarrays\), auch wenn dies zu einer Inkonsistenz der Sortierung zwischen Überladungen Parameter führt \(finden Sie unter [Überladen von Membern](../../../docs/standard/design-guidelines/member-overloading.md)\).  
  
 Die `out` Parameter können als zusätzliche Werte angezeigt werden, und gruppieren sie macht die Signatur der Methode leichter zu verstehen.  
  
 **✓ führen** Benennen von Parametern, wenn Sie Member überschreiben oder Implementieren von Schnittstellenmembern konsistent sein.  
  
 Dies besser wird die Beziehung zwischen den Methoden kommuniziert.  
  
### Auswählen zwischen Enumerationen und booleschen Parametern  
 **✓ führen** Enumerationen verwenden, wenn ein Member andernfalls mindestens zwei boolesche Parameter verfügt.  
  
 **X nicht** boolesche Werte verwenden, es sei denn, Sie sind sicher, dass es wird niemals mehr als zwei Werte benötigt werden.  
  
 Enumerationen bieten Ihnen etwas Platz für zukünftige zusätzlich Werte, aber Sie sollten über alle Aspekte des Hinzufügen von Werten zu Enumerationen, die in beschrieben werden [Enum\-Entwurf](../../../docs/standard/design-guidelines/enum.md).  
  
 **✓ ggf.** verwenden boolesche Werte für Parameter des Konstruktors, die tatsächlich von zwei Werten und einfach zur Initialisierung von boolescher Eigenschaften verwendet werden.  
  
### Überprüfen von Argumenten  
 **✓ führen** an öffentliche, geschützte oder explizit implementierten Member übergebenen Argumente zu überprüfen. Löst <xref:System.ArgumentException?displayProperty=fullName>, oder eine ihrer Unterklassen, wenn die Validierung fehlschlägt.  
  
 Beachten Sie, dass die eigentliche Überprüfung nicht notwendigerweise in der öffentlichen oder geschützten Member selbst ausgeführt. Dies kann auf einer niedrigeren Ebene in einige private oder interne Routine eintreten. Der wichtigste Aspekt ist, dass die gesamte Oberfläche, die für die Benutzer verfügbar gemacht wird, die Argumente überprüft.  
  
 **✓ führen** auslösen <xref:System.ArgumentNullException> ein null\-Argument übergeben, und das Element unterstützt keine null\-Argumente.  
  
 **✓ führen** Enum\-Parameter überprüft.  
  
 Gehen Sie nicht davon aus, dass die Enum\-Argumente in den Bereich, die durch die Enumeration definiert werden. Die CLR ermöglicht es, einen beliebigen ganzzahligen Wert in einen Enumerationswert umzuwandeln, auch wenn der Wert nicht in der Enumeration definiert ist.  
  
 **X nicht** verwenden <xref:System.Enum.IsDefined%2A?displayProperty=fullName> für Enum\-Bereich überprüft.  
  
 **✓ führen** Beachten Sie, dass änderbare Argumente nach der Überprüfung wurden geändert haben könnte.  
  
 Wenn der Member sicherheitsrelevant ist, werden Sie aufgefordert, kopieren und dann überprüfen und verarbeiten das Argument.  
  
### Parameterübergabe  
 Aus der Perspektive eines Designers Framework, es gibt drei Hauptgruppen von Parametern: Parameter als Wert `ref` Parameter und `out` Parameter.  
  
 Wenn ein Argument über einen Parameter als Wert übergeben wird, erhält das Element eine Kopie des tatsächlichen Arguments übergeben. Wenn das Argument ein Werttyp ist, wird eine Kopie des Arguments auf dem Stapel abgelegt. Wenn das Argument ein Verweistyp ist, wird eine Kopie des Verweises auf dem Stapel abgelegt. Am häufigsten verwendeten CLR\-Sprachen wie c\#, VB.NET und C\+\+ standardmäßig Parameter als Wert übergeben.  
  
 Wenn ein Argument übergeben wird, über einen `ref` \-Parameter, der Member erhält einen Verweis auf das tatsächliche Argument übergeben. Wenn das Argument ein Werttyp ist, wird ein Verweis auf das Argument auf dem Stapel abgelegt. Wenn das Argument ein Verweistyp ist, wird ein Verweis auf den Verweis auf dem Stapel abgelegt.`Ref` Parameter können verwendet werden, zu das Element so ändern Sie die Argumente, die vom Aufrufer übergeben wird.  
  
 `Out` Parameter ähneln `ref` Parametern, einige kleine Unterschiede. Der Parameter betrachtet anfänglich nicht zugewiesen und kann nicht in den Text des Elements gelesen werden, bevor ihr einen Wert zugewiesen ist. Außerdem muss der Parameter einen Wert zugewiesen werden, bevor das Element zurück.  
  
 **X vermeiden** mit `out` oder `ref` Parameter.  
  
 Mithilfe von `out` oder `ref` Parameter erfordert Erfahrung mit Zeigern, Kenntnisse der Unterschiede zwischen Wert\- und Verweistypen sowie die Behandlung von Methoden mit mehreren Rückgabewerten. Außerdem ist der Unterschied zwischen `out` und `ref` Parameter weithin nicht verstanden. Framework\-Architekten Entwerfen für eine Breite Zielgruppe sollten nicht erwarten Benutzer mit `out` oder `ref` Parameter.  
  
 **X nicht** Verweistypen als Verweis übergeben.  
  
 Es gibt einige wenige Ausnahmen von der Regel ein, z. B. eine Methode, die zum Vertauschen von Verweisen verwendet werden kann.  
  
### Member mit einer Variablen Anzahl von Parametern  
 Member, die eine Variable Anzahl von Argumenten akzeptieren können werden durch die Bereitstellung eines Arrayparameter ausgedrückt. Z. B. <xref:System.String> enthält die folgende Methode:  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 Ein Benutzer kann dann Aufrufen der <xref:System.String.Format%2A?displayProperty=fullName> \-Methode wie folgt:  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 Hinzufügen des Params\-Schlüsselworts in c\# auf einen Arrayparameter ändert der Parameter auf eine so genannte Params\-Arrayparameter und stellt eine Verknüpfung zur Erstellen eines temporären Arrays.  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 Auf diese Weise kann der Benutzer die Methode aufrufen, übergeben Sie die Elemente des Arrays direkt in der Argumentliste.  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 Beachten Sie, dass das Params\-Schlüsselwort nur der letzte Parameter in der Parameterliste hinzugefügt werden kann.  
  
 **✓ ggf.** Arrayparametern das Params\-Schlüsselwort hinzufügen, wenn Sie erwarten, die Endbenutzer zum Übergeben von Arrays mit einer kleinen Anzahl von Elementen dass. Wenn erwartet wird, dass viele Elemente in gängigen Szenarien übergeben werden, Benutzer werden wahrscheinlich nicht übergeben diese Elemente Inline trotzdem und des Params\-Schlüsselworts ist nicht erforderlich.  
  
 **X vermeiden** Params\-Arrays verwenden, wenn der Aufrufer fast immer die Eingabe in einem Array noch würde.  
  
 Member mit Byte\-Array\-Parameter würde z. B. durch Übergeben der einzelnen Bytes fast nie aufgerufen werden. Aus diesem Grund verwenden Byte\-Array\-Parameter in .NET Framework nicht des Params\-Schlüsselworts.  
  
 **X nicht** Params\-Arrays verwenden, wenn das Array von dem Member, dauert des Params\-Array\-Parameters geändert wird.  
  
 Aufgrund der Tatsache, dass viele Compiler die Argumente für das Element in ein temporäres Array an der Aufrufsite aktivieren das Array ist möglicherweise ein temporäres Objekt, und somit alle Änderungen auf das Array verloren.  
  
 **✓ ggf.** mithilfe des Params\-Schlüsselworts in einer einfachen Überladung, auch wenn es nicht von eine komplexere Überladung verwenden kann.  
  
 Fragen Sie sich, wenn Benutzer das Parameterarray in einer Überladung müssen, auch wenn es in allen Überladungen wurde nicht von Nutzen ist.  
  
 **✓ führen** versuchen, ordnen Sie Parameter des Params\-Schlüsselworts verwenden können.  
  
 **✓ ggf.** und bietet spezielle Überladungen und Codepfade für Aufrufe mit einer kleinen Anzahl von Argumenten in äußerst leistungsrelevanten APIs.  
  
 Hierdurch können Sie verhindern, dass Arrayobjekte erstellt, wenn die API mit einer kleinen Anzahl von Argumenten aufgerufen wird. Bilden Sie die Namen der Parameter im singular Schriftbild Arrayparameter und ein numerisches Suffix hinzufügen.  
  
 Sie sollten dies nur tun, wenn Sie beabsichtigen, den vollständigen Codepfad besondere Schreibweise, nicht nur ein Array erstellen, und rufen Sie die allgemeine Methode.  
  
 **✓ führen** Beachten Sie, dass Null als Params\-Arrayargument übergeben werden konnte.  
  
 Sie sollten überprüfen, dass das Array nicht vor der Verarbeitung null ist.  
  
 **X nicht** verwenden die `varargs` Methoden, die auch als Auslassungszeichen.  
  
 Einige CLR\-Sprachen, z. B. C\+\+, unterstützen eine alternative Konvention für die Übergabe von Variablen Parameterlisten namens `varargs` Methoden. Die Konvention sollte nicht in Frameworks verwendet werden, da er nicht CLS\-kompatibel ist.  
  
### Zeigerparameter  
 Im Allgemeinen Zeiger nicht in die öffentliche Oberfläche eines Frameworks ausgereifte verwalteten Code angezeigt werden soll. Die meisten Fällen sollte Zeiger gekapselt werden. In einigen Fällen Zeiger sind allerdings aus Gründen der Interoperabilität erforderlich, und Zeiger in solchen Fällen geeignet ist.  
  
 **✓ führen** bieten eine Alternative für jeden Member, der ein Zeigerargument akzeptiert, da Zeiger nicht CLS\-kompatibel sind.  
  
 **X vermeiden** teure Argument Zeigerargumente Überprüfung durchführen.  
  
 **✓ führen** Konventionen allgemeine Zeiger beim Entwerfen der Member mit Zeigern.  
  
 Beispielsweise besteht keine Notwendigkeit, den Startindex übergeben, da einfache Zeigerarithmetik verwendet werden kann, um das gleiche Ergebnis zu erzielen.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)