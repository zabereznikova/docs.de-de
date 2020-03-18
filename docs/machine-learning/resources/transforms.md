---
title: Datentransformationen
description: Untersuchen Sie die in ML.NET unterstützten herausragenden technischen Komponenten.
ms.date: 04/02/2019
ms.openlocfilehash: ca410b475c556db5ad4c3862fb79755b455d6830
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79397752"
---
# <a name="data-transformations"></a>Datentransformationen

Datentransformationen werden für Folgendes verwendet:

- Aufbereiten von Daten für das Modelltraining
- Anwenden eines importierten Modells im TensorFlow- oder ONNX-Format
- Nachverarbeiten von Daten nach dem Durchlaufen eines Modells

Die Transformationen in diesem Handbuch geben Klassen zurück, die die [IEstimator](xref:Microsoft.ML.IEstimator%601)-Schnittstelle implementieren. Datentransformationen können miteinander verkettet werden. Jede Transformation erwartet und erzeugt Daten bestimmter Typen und Formate, die in der verknüpften Referenzdokumentation angegeben werden.

Einige Datentransformationen erfordern Trainingsdaten, um ihre Parameter zu berechnen. Beispiel: Der <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A>-Transformator berechnet den Mittelwert und die Varianz der Trainingsdaten während des `Fit()`-Vorgangs und verwendet diese Parameter im `Transform()`-Vorgang.

Andere Datentransformationen erfordern keine Trainingsdaten. Beispiel: Die <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale%2A>-Transformation kann die `Transform()`-Operation durchführen, ohne während der `Fit()`-Operation Trainingsdaten gesehen zu haben.

## <a name="column-mapping-and-grouping"></a>Zuordnung und Gruppierung von Spalten

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A> | Verketten einer oder mehrerer Eingabespalten in einer neuen Ausgabespalte |
| <xref:Microsoft.ML.TransformExtensionsCatalog.CopyColumns%2A> | Kopieren und Umbenennen einer oder mehrerer Eingabespalten |
| <xref:Microsoft.ML.TransformExtensionsCatalog.DropColumns%2A> | Löschen einer oder mehrerer Eingabespalten |
| <xref:Microsoft.ML.TransformExtensionsCatalog.SelectColumns%2A> | Auswählen einer oder mehrerer beizubehaltender Spalten aus den Eingabedaten |

## <a name="normalization-and-scaling"></a>Normalisierung und Skalierung

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMeanVariance%2A> | Subtrahieren des Mittelwerts (der Trainingsdaten) und Dividieren durch die Varianz (der Trainingsdaten) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLogMeanVariance%2A> | Normalisieren auf Basis des Logarithmus der Trainingsdaten |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeLpNorm%2A> | Skalieren von Eingabevektoren durch ihre [LP-Norm](https://en.wikipedia.org/wiki/Lp_space#The_p-norm_in_finite_dimensions), wobei P gleich 1, 2 oder unendlich ist. Der Standardwert ist die L2-Norm (Euklidischer Abstand) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeGlobalContrast%2A> | Skalieren jedes Werts in einer Zeile durch Subtrahieren des Mittelwerts der Zeilendaten und Division entweder durch die Standardabweichung oder die L2-Norm (der Daten aus der Zeile) und Multiplizieren mit einem konfigurierbaren Skalierungsfaktor (Standard: 2) |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A> | Zuweisen des Eingabewerts zu einem Binindex und Division durch die Anzahl der Bins, um einen Gleitkommawert zwischen 0 und 1 zu erzeugen. Die Bingrenzen werden berechnet, um die Trainingsdaten gleichmäßig auf Bins zu verteilen |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeSupervisedBinning%2A> | Zuweisen des Eingabewerts zu einem Bin basierend auf seiner Korrelation mit der Bezeichnungsspalte |
| <xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A> | Skalieren der Eingabe um den Unterschied zwischen den minimalen und maximalen Werten in den Trainingsdaten |

## <a name="conversions-between-data-types"></a>Konvertierungen zwischen Datentypen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.ConvertType%2A> | Konvertieren des Typs einer Eingabespalte in einen neuen Typ |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValue%2A> | Zuordnen von Werten zu Schlüsseln (Kategorien) auf Grundlage des angegebenen Zuordnungenwörterbuchs |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> | Zuordnen von Werten zu Schlüsseln (Kategorien) durch Erstellen der Zuordnung aus den Eingabedaten |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A> | Konvertieren von Schlüsseln zurück in ihre ursprünglichen Werte |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToVector%2A> | Konvertieren von Schlüsseln zurück in Vektoren ursprünglicher Werte |
| <xref:Microsoft.ML.ConversionsCatalog.MapKeyToBinaryVector%2A> | Konvertieren von Schlüsseln zurück in einen binären Vektor ursprünglicher Werte |
| <xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A> | Anwenden des Hashalgorithmus auf den Wert in der Eingabespalte |

## <a name="text-transformations"></a>Texttransformationen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.TextCatalog.FeaturizeText%2A> | Umwandeln einer Textspalte in ein Gleitkommaarray der normalisierten Anzahl von N-Grammen und Char-Grammen |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A> | Aufteilen einer oder mehrerer Textspalten in einzelne Wörter |
| <xref:Microsoft.ML.TextCatalog.TokenizeIntoCharactersAsKeys%2A> | Aufteilen einer oder mehrerer Textspalten in einzelne Zeichengleitkommazahlen über eine Reihe von Themen |
| <xref:Microsoft.ML.TextCatalog.NormalizeText%2A> | Ändern von Groß-/Kleinschreibung, Entfernen von diakritischen Zeichen, Satzzeichen und Zahlen |
| <xref:Microsoft.ML.TextCatalog.ProduceNgrams%2A> | Umwandeln einer Textspalte in eine Sammlung mit der Anzahl der N-Gramme (Abfolgen aufeinander folgender Wörter)|
| <xref:Microsoft.ML.TextCatalog.ProduceWordBags%2A> | Umwandeln einer Textspalte in einen Vektor der Sammlung mit der Anzahl der N-Gramme |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedNgrams%2A> | Umwandeln einer Textspalte in einen Vektor der Anzahl von N-Grammen, für die der Hashwert berechnet wurde |
| <xref:Microsoft.ML.TextCatalog.ProduceHashedWordBags%2A> | Umwandeln einer Textspalte in eine Sammlung der Anzahl von N-Grammen, für die der Hashwert berechnet wurde |
| <xref:Microsoft.ML.TextCatalog.RemoveDefaultStopWords%2A>  | Entfernen der Standardstoppwörter für die angegebene Sprache aus Eingabespalten |
| <xref:Microsoft.ML.TextCatalog.RemoveStopWords%2A> | Entfernt die angegebenen Stoppwörter aus Eingabespalten |
| <xref:Microsoft.ML.TextCatalog.LatentDirichletAllocation%2A> | Umwandeln eines Dokuments (dargestellt als Vektor von Gleitkommazahlen) in einen Vektor von Gleitkommazahlen über eine Reihe von Themen |
| <xref:Microsoft.ML.TextCatalog.ApplyWordEmbedding%2A> | Konvertieren von Vektoren von Texttoken in Satzvektoren mithilfe eines vortrainierten Modells |

## <a name="image-transformations"></a>Bildtransformationen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToGrayscale%2A> | Konvertieren eines Bilds in Graustufen |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ConvertToImage%2A> | Konvertieren eines Vektors von Pixeln in <xref:Microsoft.ML.Transforms.Image.ImageDataViewType> |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ExtractPixels%2A> | Konvertieren von Pixeln eines Eingabebilds in einen Vektor aus Zahlen |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.LoadImages%2A> | Laden von Bildern aus einem Ordner in den Arbeitsspeicher |
| <xref:Microsoft.ML.ImageEstimatorsCatalog.ResizeImages%2A> | Ändern der Größe von Bildern |
| <xref:Microsoft.ML.OnnxCatalog.DnnFeaturizeImage%2A> | Wendet ein vortrainiertes DNN-Modell (Deep Neural Network) an, um ein Eingabebild in einen Merkmalsvektor zu transformieren |

## <a name="categorical-data-transformations"></a>Kategorische Datentransformationen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A> | Konvertieren einer oder mehrerer Textspalten in mit [1-aus-n-Code](https://en.wikipedia.org/wiki/One-hot) codierte Vektoren |
| <xref:Microsoft.ML.CategoricalCatalog.OneHotHashEncoding%2A> | Konvertieren mindestens einer Textspalte in hashbasierte one-hot-codierte Vektoren |

## <a name="time-series-data-transformations"></a>Zeitreihendaten-Transformationen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectAnomalyBySrCnn%2A> | Erkennen von Anomalien in den Eingabe-Zeitreihendaten mit dem SR-Algorithmus (Spectral Residual Algorithm) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectChangePointBySsa%2A> | Erkennen von Änderungspunkten in Zeitreihendaten mithilfe von SSA (Singular Spectrum Analysis) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectIidChangePoint%2A> | Erkennen von Änderungspunkten in unabhängigen und identisch verteilten Zeitreihendaten (IID) mithilfe adaptiver Kerneldichteschätzungen und Martingalbewertungen |
| <xref:Microsoft.ML.TimeSeriesCatalog.ForecastBySsa%2A> | Vorhersagen von Zeitreihendaten mithilfe von SSA (Singular Spectrum Analysis) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectSpikeBySsa%2A> | Erkennen von Spitzen in Zeitreihendaten mithilfe von SSA (Singular Spectrum Analysis) |
| <xref:Microsoft.ML.TimeSeriesCatalog.DetectIidSpike%2A> | Erkennen von Spitzen in unabhängigen und identisch verteilten Zeitreihendaten (IID) mithilfe adaptiver Kerneldichteschätzungen und Martingalbewertungen |

## <a name="missing-values"></a>Fehlende Werte

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.ExtensionsCatalog.IndicateMissingValues%2A> | Erstellen einer neuen booleschen Ausgabespalte, deren Wert „true“ ist, wenn der Wert in der Eingabespalte fehlt |
| <xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A> | Erstellen einer neuen Ausgabespalte, deren Wert auf einen Standardwert festgelegt ist, wenn der Wert aus der Eingabespalte nicht vorhanden ist, und andernfalls auf den Eingabewert |

## <a name="feature-selection"></a>Featureauswahl

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnCount%2A> | Auswählen von Features, deren nicht standardmäßige Werte größer als der Schwellenwert sind |
| <xref:Microsoft.ML.FeatureSelectionCatalog.SelectFeaturesBasedOnMutualInformation%2A> | Wählen Sie die Features aus, von denen die Daten in der Bezeichnungsspalte am meisten abhängen |

## <a name="feature-transformations"></a>Merkmalstransformationen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.KernelExpansionCatalog.ApproximatedKernelMap%2A> | Zuordnen jedes Eingabevektors zu einem Merkmalsraum einer niedrigeren Dimension, wobei die inneren Produkte einer Kernelfunktion nahe kommen, damit die Merkmale als Eingaben für die linearen Algorithmen verwendet werden können |
| <xref:Microsoft.ML.PcaCatalog.ProjectToPrincipalComponents%2A> | Verringern der Dimensionen des Eingabemerkmalsvektors durch Anwenden des Algorithmus für die Hauptkomponentenanalyse |

## <a name="explainability-transformations"></a>Erklärbarkeitstransformationen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.ExplainabilityCatalog.CalculateFeatureContribution%2A> | Berechnen der Beitragsbewertungen für jedes Element eines Merkmalsvektors |

## <a name="calibration-transformations"></a>Kalibrierungstransformationen

| Transformation | Definition |
| --- | --- |
|<xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Platt%28System.String%2CSystem.String%2CSystem.String%29> | Transformieren der Rohbewertung eines binären Klassifizierers in eine Klassenwahrscheinlichkeit unter Verwendung der logistischen Regression mit anhand der Trainingsdaten geschätzten Parametern |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Platt%28System.Double%2CSystem.Double%2CSystem.String%29> | Transformieren der Rohbewertung eines binären Klassifizierers in eine Klassenwahrscheinlichkeit unter Verwendung der logistischen Regression mit festen Parametern |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Naive%2A> | Transformieren der Rohbewertung eines binären Klassifizierers in eine Klassenwahrscheinlichkeit durch Zuweisen von Bewertungen zu Fächern und Berechnen der Wahrscheinlichkeit basierend auf der Binominalverteilung |
| <xref:Microsoft.ML.BinaryClassificationCatalog.CalibratorsCatalog.Isotonic%2A> | Transformieren der Rohbewertung eines binären Klassifizierers in eine Klassenwahrscheinlichkeit durch Zuweisen von Bewertungen zu Fächern, wobei die Position der Begrenzungen und die Größe der Fächer anhand der Trainingsdaten geschätzt werden  |

## <a name="deep-learning-transformations"></a>Deep Learning-Transformationen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.OnnxCatalog.ApplyOnnxModel%2A> | Transformieren der Eingabedaten mit einem importierten ONNX-Modell |
| <xref:Microsoft.ML.TensorflowCatalog.LoadTensorFlowModel%2A> | Transformieren der Eingabedaten mit einem importierten TensorFlow-Modell |

## <a name="custom-transformations"></a>Benutzerdefinierte Transformationen

| Transformation | Definition |
| --- | --- |
| <xref:Microsoft.ML.CustomMappingCatalog.CustomMapping%2A> | Transformieren vorhandener Spalten in neue mit einer benutzerdefinierten Zuordnung |
