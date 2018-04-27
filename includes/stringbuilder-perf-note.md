Das Verwenden von zeichenbasierter Indizierung mit der <xref:System.Text.StringBuilder.Chars%2A>-Eigenschaft kann unter folgenden Bedingungen sehr langsam sein:

- Die <xref:System.Text.StringBuilder>-Instanz ist groß, weil sie beispielsweise aus Zehntausenden von Zeichen besteht.
- <xref:System.Text.StringBuilder> ist „blockweise“ strukturiert. Das bedeutet, dass wiederholte Aufrufe von Methoden (z.B. <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>) die <xref:System.Text.StringBuilder.Capacity%2A?displayProperty=nameWithType>-Eigenschaft des Objekts automatisch erweitert haben und dieser neue Arbeitsspeicherblöcke zugeordnet haben.

Die Leistung wird erheblich beeinträchtigt, da für jeden Zugriff auf ein Zeichen die gesamte verknüpfte Liste der Blöcke durchlaufen wird, um den richtigen Puffer für die Indizierung zu suchen.

> [!NOTE]
>  Auch für ein „blockweise“ strukturiertes <xref:System.Text.StringBuilder>-Objekt kann das Verwenden der <xref:System.Text.StringBuilder.Chars%2A>-Eigenschaft für den indexbasierten Zugriff auf ein oder wenige Zeichen eine negative Auswirkung auf die Leistung haben. Üblicherweise handelt es sich dabei um eine **0(n)**-Operation. Diese erheblichen Auswirkungen auf die Leistung treten auf, wenn die Zeichen im <xref:System.Text.StringBuilder>-Objekt durchlaufen werden. Dabei handelt es sich um eine **O(n^2)**-Operation. 

Wenn Leistungsprobleme auftreten, wenn Sie die zeichenbasierte Indizierung mit <xref:System.Text.StringBuilder>-Objekten verwenden, können Sie eine der folgenden Problemumgehungen anwenden:

- Konvertieren Sie die <xref:System.Text.StringBuilder>-Instanz zu <xref:System.String>, indem Sie die <xref:System.Text.StringBuilder.ToString%2A>-Methode aufrufen. Greifen Sie dann auf die Zeichen in der Zeichenfolge zu.

- Kopieren Sie die Inhalte des vorhandenen <xref:System.Text.StringBuilder>-Objekts in ein neues <xref:System.Text.StringBuilder>-Objekt mit vorab festgelegter Größe. Die Leistung verbessert sich, da das neue <xref:System.Text.StringBuilder>-Objekt nicht „blockweise“ strukturiert ist. Zum Beispiel:

   ```csharp
   // sbOriginal is the existing StringBuilder object
   var sbNew = new StringBuilder(sbOriginal.ToString(), sbOriginal.Length);
   ```
   ```vb
   ' sbOriginal is the existing StringBuilder object
   Dim sbNew = New StringBuilder(sbOriginal.ToString(), sbOriginal.Length)
   ```
- Legen Sie die anfängliche Kapazität des <xref:System.Text.StringBuilder>-Objekts auf einen Wert fest, der ungefähr der maximal erwarteten Größe entspricht, indem der <xref:System.Text.StringBuilder.%23ctor(System.Int32)>-Konstruktor aufgerufen wird. Beachten Sie, dass dadurch der gesamte Arbeitsspeicherblock zugeordnet wird, auch wenn <xref:System.Text.StringBuilder> selten die maximale Kapazität erreicht.
