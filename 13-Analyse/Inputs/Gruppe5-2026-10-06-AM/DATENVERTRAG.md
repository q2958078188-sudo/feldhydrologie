# Datenvertrag: Gruppe 5, Dienstagvormittag 06.10.2026

- `Kalibrierung-Visualisierung.json`: kompatibel zu `bodensensorik-calibration-v1`, 11 tatsächliche Punkte 0-10. Zahlen sind numeric/null; Originale und ungerundete Dezimalwerte bleiben zusätzlich erhalten.
- MP 10 ist die neueste Ablesung **0.467**. Seine 600 mL werden einmal gezählt; insgesamt **3300 mL** zugesetzt. Früheres 0.443 steht nur im Originalverlauf.
- MP 1 bleibt sichtbar, hat `quantitative_analysis_include=false`, `reference_calibration_pair_include=false`, `calibration_fit_include=false`.
- MP 10 bleibt sichtbar; wegen Wasseransammlung `reference_calibration_pair_include=false`, `calibration_fit_include=false`. Sein `theta_ref_m3_m3` ist **nur der Gesamtwasser-Bilanzwert**, kein nachgewiesener Porenwasserwert. `theta_bias_m3_m3=null`; die formale Differenz steht separat unter `theta_ledger_difference_m3_m3`.
- Neun übrige Paare sind für den deskriptiven Vergleich freigegeben, keine Regression ist durchgeführt. Die Referenz hängt von Kurs-w0 und konstant angenommenem Packungsvolumen ab.
- `RAW` ist aus θMETER rückgerechnet (`raw_basis=derived_inverse_of_theta_meter`), **kein direkt gemessener Rohwert**. Keine unabhängige RAW-Kalibrierung/Regression ableiten.
- `matrix_kpa` bleibt in sämtlichen Kalibrierpunkten null: -4.3 und ungefähr -11 kPa wurden im **ungesiebten Ausgangsboden** nebenher beobachtet, nicht im Kalibrierboden. Sie stehen ausschließlich in `parallel_observations` bzw. `Unabhaengige-Beobachtungen.json`. Keine θ-ψ-Paarung oder Retentionskurve.
- Reines Wasser 0.678 ist ein **separater Funktionstest im Mineralbodenmodus**, vollständig eingetauchte gleiche TEROS-11-Sonde. Keine Zugabe zur Kalibrierprobe, kein zusätzlicher Bodenpunkt, kein θref=1 als Fehlermaßstab.
- `KA6-Visualisierung.json`: `bodensensorik-ka6-v1`, fünf Kurskenngrößen x vier Spalten, alle explizit bestätigtes TRD1. Ts3 bleibt Fingerprobe-Schätzung. Die 20 Werte sind Tabellenwerte, keine Kapazitätsmessungen. Zellquellen und SHA der Kursdatei sind erhalten, GPV=FK+LK.
- `source_row=null`, weil die autoritative Quelle JSON/gezielte Zellwerte und kein ausgefülltes Excel-Messblatt ist. `source_pointer`, `source_fields` und stabile `record_id` liefern exakte Herkunft ohne fiktive Tabellenzeilen.
- Keine Messpunkt-Uhrzeiten, Wiederholungszahlen, Mittelwerte oder Fehlerbalken hinzugefügt. 09:00-ca.12:00 ist nur das vom Nutzer bestätigte Gesamtintervall.
- Keine Übernahme in leere offizielle Messvorlagen und keine Site-Veröffentlichung in diesem Asset-Schritt.
