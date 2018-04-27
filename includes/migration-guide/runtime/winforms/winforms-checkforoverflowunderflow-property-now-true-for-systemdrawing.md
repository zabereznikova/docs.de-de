### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>Die CheckForOverflowUnderflow-Eigenschaft von WinForm ist jetzt für System.Drawing auf TRUE festgelegt

|   |   |
|---|---|
|Details|Die CheckForOverflowUnderflow-Eigenschaft für die Assembly „System.Drawing.dll“ ist auf TRUE festgelegt.|
|Vorschlag|Zuvor wurde das Ergebnis im Fall von Überläufen automatisch abgeschnitten. Nun wird eine <xref:System.OverflowException?displayProperty=name>-Ausnahme ausgelöst.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

