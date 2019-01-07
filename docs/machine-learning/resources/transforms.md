---
title: Datentransformationen für maschinelles Lernen – ML.NET
description: Untersuchen Sie die in ML.NET unterstützten herausragenden technischen Komponenten.
author: JRAlexander
ms.custom: seodec18
ms.date: 12/14/2018
ms.openlocfilehash: 72e4077151d35b9bff661c28c9a20626098a5c69
ms.sourcegitcommit: 882a2f56bf6afdcb40d468e4ae9371296822b68c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2018
ms.locfileid: "53451091"
---
# <a name="machine-learning-data-transforms---mlnet"></a>Datentransformationen für maschinelles Lernen – ML.NET

Die folgenden Tabellen enthalten Informationen über alle in ML.NET unterstützten Datentransformationen.

> [!NOTE]
> ML.NET ist derzeit als Vorschauversion verfügbar. Nicht alle Datentransformationen werden derzeit unterstützt. Wenn Sie eine Anforderung für eine bestimmte Transformation einreichen möchten, können Sie ein Issue im GitHub-Repository [dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues) erstellen.

## <a name="combiners-and-segregators"></a>Kombinierer und Trenner

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Transforms.GroupTransform> | Gruppiert Werte einer Skalarspalte auf Grundlage einer ID einer zusammenhängenden Gruppe und überführt diese in einen Vektor. |
| <xref:Microsoft.ML.Legacy.Transforms.FeatureCombiner> | Kombiniert alle Features und überführt diese in eine Featurespalte. |
| <xref:Microsoft.ML.Legacy.Transforms.ManyHeterogeneousModelCombiner> | Kombiniert eine Sequenz von TransformModel-Eigenschaften und eine PredictorModel-Eigenschaft und überführt diese in eine einzelne PredictorModel-Eigenschaft. |
| <xref:Microsoft.ML.Legacy.Transforms.ModelCombiner> | Kombiniert eine Sequenz von TransformModel-Eigenschaften und überführt diese in ein einzelnes Modell. |
| <xref:Microsoft.ML.Legacy.Transforms.Segregator> | Hebt die Gruppierung für Vektorspalten auf und überführt diese in Zeilensequenzen; Umkehrvorgang zur Gruppentransformation. |
| <xref:Microsoft.ML.Legacy.Transforms.TwoHeterogeneousModelCombiner> | Kombiniert eine TransformModel- und PredictorModel-Eigenschaft und überführt diese in eine einzelne PredictorModel-Eigenschaft. |
| <xref:Microsoft.ML.Transforms.UngroupTransform> | Hebt die Gruppierung für Vektorspalten auf und überführt diese in Zeilensequenzen; Umkehrvorgang zur Gruppentransformation. |

## <a name="conversions"></a>Konvertierungen 

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Conversions.HashingTransformer> | Bildet Hashwerte entweder aus Spalten mit Einzelwerten oder aus Vektorspalten. Bei Vektorspalten wird für jeden Slot ein separater Hashwert gebildet. Hashwerte können wahlweise aus Textwerten oder aus Schlüsselwerten gebildet werden. |
| <xref:Microsoft.ML.Legacy.Transforms.HashConverter> | Konvertiert die Spaltenwerte in Hashwerte. Für diese Transformation werden sowohl Texteingaben als auch numerische Eingaben akzeptiert. Es kann sich sowohl um Spalten mit Einzel- als auch mit Vektorwerten handeln. |
| <xref:Microsoft.ML.Transforms.Conversions.HashJoiningTransform> | Konvertiert mehrere Spaltenwerte in Hashwerte. Für diese Transformation werden sowohl Texteingaben als auch numerische Eingaben akzeptiert. Es kann sich sowohl um Spalten mit Einzel- als auch mit Vektorwerten handeln. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToBinaryVectorMappingTransformer> | Konvertiert einen Schlüssel in eine binäre Vektorspalte. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToValueMappingTransformer > | Nutzt KeyValues-Metadaten, um die Schlüsselindizes den entsprechenden Werten in den KeyValues-Metadaten zuzuordnen. |
| <xref:Microsoft.ML.Transforms.Conversions.KeyToVectorMappingTransformer> | Konvertiert einen Schlüssel in eine Vektorspalte. |
| <xref:Microsoft.ML.Transforms.Conversions.TypeConvertingTransformer> | Ändert den zugrundeliegenden Spaltentyp, vorausgesetzt, der Typ kann konvertiert werden. |
| <xref:Microsoft.ML.Transforms.Conversions.ValueToKeyMappingTransformer> | Konvertiert Eingabewerte (Wörter, Zahlen usw.) für eine Wörterbuchindizierung. |


## <a name="deep-learning"></a>Deep Learning

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Transforms.OnnxTransform> | Stellt Daten für ein vorhandenes ONNX-Modell zur Verfügung und gibt die Bewertung zurück (Vorhersage). |
| <xref:Microsoft.ML.Transforms.TensorFlowTransform> | Kann entweder eine Bewertung eines vortrainierten TensorFlow-Modells oder das erneute Trainieren eines TensorFlow-Modells durchführen. |

## <a name="feature-extraction"></a>Featureextraktion

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Text.CustomStopWordsRemovingTransform> | Entfernt eine angegebene Liste von Stoppwörtern durch Vergleich einzelner Token (ohne Berücksichtigung der Groß-/Kleinschreibung) mit den Stoppwörtern.| 
| <xref:Microsoft.ML.Runtime.ImageAnalytics.ImageGrayscaleTransform> | Nimmt eine oder mehrere ImageType-Spalten an und konvertiert sie in eine Graustufendarstellung des gleichen Bilds.|
| <xref:Microsoft.ML.Runtime.ImageAnalytics.ImageLoaderTransform> | Nimmt eine oder mehrere ReadOnlyMemory-Spalten an und lädt sie als einen ImageType. |
| <xref:Microsoft.ML.Runtime.ImageAnalytics.ImagePixelExtractorTransform> | Nimmt eine oder mehrere ImageType-Spalten an und konvertiert sie in eine Vektordarstellung.|
| <xref:Microsoft.ML.Runtime.ImageAnalytics.ImageResizerTransform> | Nimmt eine oder mehrere ImageType-Spalten an und ändert ihre Größe auf die angegebene Höhe und Breite.|
| <xref:Microsoft.ML.Transforms.Text.LatentDirichletAllocationTransformer> | Implementiert LightLDA, eine Implementierung der Latent Dirichlet Allocation auf dem neuesten Stand.|
| <xref:Microsoft.ML.Transforms.LoadTransform> | Lädt bestimmte Transformationen aus der angegebenen Modelldatei. Ermöglicht die gezielte Auswahl von Transformationen aus einer serialisierten Kette oder die Anwendung einer vortrainierten Transformation auf eine andere (aber trotzdem kompatible) Datenansicht. |
| <xref:Microsoft.ML.Transforms.Text.NgramExtractingTransformer> | Erstellt eine Sammlung mit der Anzahl der N-Gramme (Sequenzen aufeinander folgender Werte der Länge 1–n) in einem angegebenen Schlüsselvektor. Dabei wird ein Wörterbuch mit N-Grammen erstellt, und die ID im Wörterbuch wird als Index in der Sammlung verwendet. | 
| <xref:Microsoft.ML.Transforms.Text.NgramExtractorTransform> | Wandelt eine Sammlung von Tokentext (Vektor von ReadOnlyMemory) oder Vektoren von Schlüsseln in numerische Featurevektoren um. Die Featurevektoren sind die Anzahlen von N-Grammen (Abfolgen aufeinander folgender Token – Wörter oder Schlüssel – mit der Länge 1-n). | 
| <xref:Microsoft.ML.Transforms.Text.NgramHashExtractingTransformer> | Wandelt eine Sammlung von Tokentext (Vektor von ReadOnlyMemory) mittels Hashing in numerische Featurevektoren um. | 
| <xref:Microsoft.ML.Transforms.Text.NgramHashingTransformer> | Erzeugt eine Sammlung mit der Anzahl der N-Gramme (Abfolgen aufeinander folgender Wörter der Länge 1–n) in einem bestimmten Text. | 
| <xref:Microsoft.ML.Transforms.Categorical.OneHotEncodingTransformer> | Konvertiert den Kategoriewert in ein Indikatorarray. Dazu wird auf der Grundlage der Daten ein Wörterbuch der Kategorien erstellt und die ID im Wörterbuch als Index im Array verwendet. |
| <xref:Microsoft.ML.Transforms.Projections.PcaTransform> | Berechnet die Projektion des Featurevektors auf einen niederrangigen Teilraum. |
| <xref:Microsoft.ML.Transforms.Text.SentimentAnalyzingTransformer> | Verwendet ein vortrainiertes Stimmungsmodell, um Eingabezeichenfolgen zu bewerten. |
| <xref:Microsoft.ML.Transforms.Text.StopWordsRemovingTransformer> | Entfernt eine sprachspezifische Liste von Stoppwörtern (häufigsten Wörtern) durch Vergleich einzelner Token (ohne Berücksichtigung der Groß-/Kleinschreibung) mit den Stoppwörtern. |
| <xref:Microsoft.ML.Transforms.Categorical.TermLookupTransformer> | Ordnet Spalten mit Textwerten mithilfe eines Zuordnungsdatasets, das durch seine Argumente bereitgestellt wird, neuen Spalten zu. |
| <xref:Microsoft.ML.Transforms.Text.WordBagBuildingTransformer> | Erzeugt eine Sammlung mit der Anzahl der N-Gramme (Abfolgen aufeinander folgender Wörter) in einem bestimmten Text. Dabei wird ein Wörterbuch mit N-Grammen erstellt, und die ID im Wörterbuch wird als Index in der Sammlung verwendet. |
| <xref:Microsoft.ML.Transforms.Text.WordHashBagProducingTransformer> | Erzeugt eine Sammlung mit der Anzahl der N-Gramme (Abfolgen aufeinander folgender Wörter der Länge 1–n) in einem bestimmten Text. Dazu wird ein Hashwert jedes N-Gramms erstellt, der dann als Index in der Sammlung verwendet wird. |
| <xref:Microsoft.ML.Transforms.Text.WordTokenizingTransformer> | Teilt den Text mithilfe der Trennzeichen in Wörter auf. |


## <a name="image-model-featurizers"></a>Featurebereitsteller von Bildmodellen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Transforms.AlexNetExtension> | Dies ist eine Erweiterungsmethode für die Verwendung mit dem <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator>, um ein vortrainiertes [AlexNet](https://en.wikipedia.org/wiki/AlexNet)-Modell zu verwenden. Das NuGet-Paket, das diese Erweiterung enthält, beinhaltet außerdem garantiert die binäre Modelldatei. | 
| <xref:Microsoft.ML.Transforms.ResNet18Extension> | Diese ist eine Erweiterungsmethode für die Verwendung mit dem <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator>, um ein vortrainiertes ResNet18-Modell zu verwenden. Das NuGet-Paket, das diese Erweiterung enthält, beinhaltet außerdem garantiert die binäre Modelldatei. |
| <xref:Microsoft.ML.Transforms.ResNet50Extension> | Diese ist eine Erweiterungsmethode für die Verwendung mit dem <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator>, um ein vortrainiertes ResNet50-Modell zu verwenden. Das NuGet-Paket, das diese Erweiterung enthält, beinhaltet außerdem garantiert die binäre Modelldatei. |
| <xref:Microsoft.ML.Transforms.ResNet101Extension> | Diese ist eine Erweiterungsmethode für die Verwendung mit dem <xref:Microsoft.ML.Transforms.DnnImageFeaturizerEstimator>, um ein vortrainiertes ResNet101-Modell zu verwenden. Das NuGet-Paket, das diese Erweiterung enthält, beinhaltet außerdem garantiert die binäre Modelldatei. |

## <a name="label-parsing"></a>Bezeichnungsanalyse

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Legacy.Transforms.Dictionarizer> | Konvertiert Eingabewerte (Wörter, Zahlen usw.) für eine Wörterbuchindizierung. |
| <xref:Microsoft.ML.Legacy.Transforms.LabelColumnKeyBooleanConverter> | Transformiert die Bezeichnung entweder in einen Schlüssel oder einen booleschen Wert (falls erforderlich), damit diese zur Klassifizierung verwendet werden kann. |
| <xref:Microsoft.ML.Transforms.LabelConvertTransform> |  Konvertiert Bezeichnungen. |
| <xref:Microsoft.ML.Transforms.LabelIndicatorTransform> | Ordnet mehrklassige Bezeichnungen binären WAHR-, FALSCH-Bezeichnungen neu zu, hauptsächlich für die Verwendung mit OVA.|
| <xref:Microsoft.ML.Legacy.Transforms.LabelToFloatConverter> | Transformiert die Bezeichnung in einen Gleitkommawert, damit diese für die Regression verwendet werden kann. |
| <xref:Microsoft.ML.Legacy.Transforms.PredictedLabelColumnOriginalValueConverter> | Transformiert eine Spalte mit vorhergesagten Bezeichnungen in ihre Originalwerte. Gilt nicht für boolesche Spalten. |

## <a name="missing-values"></a>Fehlende Werte

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Transforms.MissingValueDroppingTransformer> | Entfernt fehlende Werte aus Spalten. |
| <xref:Microsoft.ML.Transforms.MissingValueIndicatorTransform> | Erstellt eine boolesche Ausgabespalte, in der sich genauso viele Slots wie in der Eingabespalte befinden. Der Ausgabewert ist TRUE, falls der Wert in der Eingabespalte fehlt. |
| <xref:Microsoft.ML.Transforms.MissingValueReplacingTransformer> | Ersetzt fehlende Werte durch den Standardwert oder durch den Mittel-, Mindest- oder Höchstwert (nur im Fall von Nicht-Text-Spalten). |
| <xref:Microsoft.ML.Transforms.MissingValueIndicatorTransform> | Erstellt eine boolesche Ausgabespalte, in der sich genauso viele Slots wie in der Eingabespalte befinden. Der Ausgabewert ist TRUE, falls der Wert in der Eingabespalte fehlt. |

## <a name="normalization"></a>Normalisierung

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Projections.LpNormalizingTransformer> | Lp-Norm-Normalisierungstransformation (vektor-/zeilenweise). |
| <xref:Microsoft.ML.Transforms.Normalizers.MeanVarDblAggregator> | Berechnet Mittelwert und Abweichung für eine Spalte mit Vektorwerten. Verfolgt den aktuellen Mittelwert und den M2 (Summe der zum Quadrat erhobenen Differenzen der Werte des Mittelwerts), die Anzahl der NaNs und die Anzahl der Elemente ungleich Null nach. |
| <xref:Microsoft.ML.Transforms.Normalizers.MeanVarSngAggregator> | Berechnet Mittelwert und Abweichung für eine Spalte mit Vektorwerten. Verfolgt den aktuellen Mittelwert und den M2 (Summe der zum Quadrat erhobenen Differenzen der Werte des Mittelwerts), die Anzahl der NaNs und die Anzahl der Elemente ungleich Null nach. |
| <xref:Microsoft.ML.Transforms.Normalizers.MinMaxDblAggregator> | Verfolgt die Minimal- und Maximalanzahl der Werte nicht geringer Dichte (vCount) und die Anzahl der ProcessValue()-Aufrufe (trainCount) für eine Spalte mit Vektorwerten. |
| <xref:Microsoft.ML.Transforms.Normalizers.MinMaxSngAggregator> | Verfolgt die Minimal- und Maximalanzahl der Werte nicht geringer Dichte (vCount) und die Anzahl der ProcessValue()-Aufrufe (trainCount) für eine Spalte mit Vektorwerten. |
| <xref:Microsoft.ML.Transforms.Normalizers.NormalizeTransform> | Standardisiert Featurebereiche. |
| <xref:Microsoft.ML.Transforms.Normalizers.NormalizingTransformer> |Standardisiert Featurebereiche. |

## <a name="onnx"></a>Onnx

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Transforms.OnnxTransform> | Bewertet vortrainierte ONNX-Modelle, die den ONNX v1.2-Standard verwenden. |

## <a name="preprocessing"></a>Vorverarbeitung
| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Transforms.BootstrapSamplingTransformer> | Erzeugt eine Annäherung an Bootstrap-Zufallsstichproben mithilfe von Poisson-Zufallsstichproben. |
| <xref:Microsoft.ML.Transforms.Projections.RandomFourierFeaturizingTransformer> | Generiert eine zufällige Fourierfunktion. |
| <xref:Microsoft.ML.Transforms.Text.TokenizingByCharactersTransformer> | Zeichenorientierter Tokenizer, der Text als Zeichensequenz verarbeitet. |
| <xref:Microsoft.ML.Transforms.Projections.VectorWhiteningTransformer> | Vereinfacht die Optimierung, unterstützend bei der Erkennung von Gewichtungen verwendet. |

## <a name="row-filters"></a>Zeilenfilter

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Transforms.RowShufflingTransformer> | Mischt einen randomisierten Cursor bei einem Ausführungsversuch und verwendet dazu einen Pool aus einer bestimmten Anzahl Zeilen.  |
| <xref:Microsoft.ML.Transforms.SkipFilter> | Ermöglicht das Einschränken der Eingabe auf eine Teilmenge von Zeilen, indem eine bestimmte Anzahl von Zeilen übersprungen wird. |
| <xref:Microsoft.ML.Transforms.SkipTakeFilter> | Ermöglicht das Einschränken der Eingabe auf eine Teilmenge von Zeilen unter Berücksichtigung eines optionalen Offsets. Kann zur Implementierung eines Seitensteuerungsverfahrens für Daten verwendet werden. Verhält sich bei Erstellung mit SkipTakeFilter.SkipArguments wie `SkipFilter`.
| <xref:Microsoft.ML.Transforms.TakeFilter> | Ermöglicht das Einschränken der Eingabe auf eine Teilmenge von Zeilen, indem die ersten N Zeilen berücksichtigt werden. |


## <a name="schema"></a>Schema

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Transforms.ColumnCopyingTransformer> | Dupliziert die Spalten aus dem Dataset.|
| <xref:Microsoft.ML.Transforms.ColumnSelectingTransformer> | Wählt einen Satz von Spalten aus, die in einer bestimmten Eingabe gelöscht oder beibehalten werden sollen. |
| <xref:Microsoft.ML.Transforms.FeatureSelection.SlotsDroppingTransformer> | Löscht Slots aus Spalten.|
| <xref:Microsoft.ML.Legacy.Transforms.KeyToTextConverter> | KeyToValueTransform nutzt KeyValues-Metadaten, um die Schlüsselindizes den entsprechenden Werten in den KeyValues-Metadaten zuzuordnen. |
| <xref:Microsoft.ML.Transforms.OptionalColumnTransform> | Erstellt eine neue Spalte vom angegebenen Typ mit Standardwerten. |
| <xref:Microsoft.ML.Transforms.RangeFilter> | Filtert eine Datensicht nach einer Spalte des Typs „Single“, „Double“ oder nach ihrem Schlüssel (zusammenhängende Gruppe). Behält die Werte bei, die im Bereich zwischen angegebenem Minimum und Maximum liegen. Fehlende Werte werden stets herausgefiltert. Wenn die Eingabe ein Schlüssel ist, werden die minimalen/maximalen Werte als Prozentsätze der Anzahl der Werte betrachtet. |

## <a name="tensorflow"></a>TensorFlow

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Transforms.TensorFlowTransform> | Führt entweder eine Bewertung eines vortrainierten TensorFlow-Modells oder das erneute Trainieren eines TensorFlow-Modells durch. |

## <a name="text-processing-and-featurization"></a>Textverarbeitung und Featurebereitstellung

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Transforms.Text.TextNormalizingTransformer> | Eine Normalisierungstransformation von Text, die Normalisierung der Groß-/Kleinschreibung, das Entfernen von diakritischen Zeichen und/oder Ziffern ermöglicht. Die Transformation wird auf Texteingabe sowie als Vektor von Token/Text ausgeführt (Vektor von ReadOnlyMemory). |
| <xref:Microsoft.ML.Transforms.Text.TokenizingByCharactersTransformer> | Zeichenorientierter Tokenizer, der Text als Zeichensequenz verarbeitet. |

## <a name="time-series"></a>Zeitreihe

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.ExponentialAverageTransform> | Akzeptiert einen gewichteten Mittelwert der Werte: ExpAvg(y_t) = a * y_t + (1-a) * ExpAvg(y_(t-1)). |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.IidChangePointDetector> | Implementiert die Transformation der Änderungspunkterkennung für eine u.i.v. Sequenz (Zufallsstichprobe) basierend auf der Schätzung der adaptiven Kerneldichte und Martingalen. |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.IidSpikeDetector> | Implementiert die Transformation der Spitzenerkennung für eine u.i.v. Sequenz (Zufallsstichprobe) basierend auf der Schätzung der adaptiven Kerneldichte. |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.MovingAverageTransform> | Stellt einen gewichteten Durchschnitt der Werte des gleitenden Fensters bereit. |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.PercentileThresholdTransform> | Entscheidet, ob der aktuelle Wert der Zeitreihe zum Perzentil der höchsten Werte des gleitenden Fensters gehört. |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.PValueTransform> | Berechnet den empirischen p-Wert des aktuellen Werts der Reihe auf der Grundlage der anderen Werte im gleitenden Fenster. |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.SlidingWindowTransform> | Gibt ein gleitendes Fenster über eine Zeitreihe vom Typ Single aus. |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.SsaChangePointDetector> | Implementiert die Transformation der Änderungspunkterkennung auf der Grundlage der Einzelspektrum-Modellierung der Zeitreihe. |
| <xref:Microsoft.ML.Runtime.TimeSeriesProcessing.SsaSpikeDetector> | Implementiert die Transformation der Spitzenerkennung auf der Grundlage der Einzelspektrum-Modellierung der Zeitreihe. |

## <a name="miscellaneous"></a>Verschiedenes

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.Transforms.CompositeTransformer> | Erstellt eine zusammengesetzte DataTransform. |
| <xref:Microsoft.ML.Transforms.CustomMappingTransformer%602> | Generiert zusätzliche Spalten für die bereitgestellte `IDataView`. Die Anzahl der Zeilen wird nicht geändert, und der Vorgang kann als Ergebnis der Anwendung der Funktion des Benutzers auf jede Zeile der Eingabedaten angesehen werden.|
| <xref:Microsoft.ML.Transforms.GenerateNumberTransform> | Fügt eine Spalte mit einer generierten Zahlensequenz hinzu. |
| <xref:Microsoft.ML.Transforms.ProduceIdTransform> | Erzeugt eine Spalte mit der ID des Cursors als Spalte. |
| <xref:Microsoft.ML.Transforms.RandomNumberGenerator> | Generiert eine zufällige Zahl. |
| <xref:Microsoft.ML.Transforms.ScoringTransformer> | Kombiniert Informationen aus mehreren Vorhersagemodellen, um ein neues Modell in der Pipeline zu erstellen. Dazu werden die Bewertungen aus einem bereits trainierten Modell verwendet. |
