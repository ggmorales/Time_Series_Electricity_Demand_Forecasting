Descripción de la base de datos:
Fue extraida de Kaggle y abarca datos entre el 1 de enero de 2015 y el 6 de octubre de 2020. Durante algunos intervalos intradiarios, la PRR fue negativa, por lo que eran los productores de energía los que pagaban a los consumidores y no a la inversa. A continuación se ofrece una breve descripción de los datos.

- date: datetime, la fecha del registro.
- demanda: flotante, la demanda diaria total de electricidad en MWh.
- **RRP**: float, precio minorista recomendado en AUD$ / MWh.
- **demand_pos_RRP**: float, una demanda diaria total a RRP positivo en MWh.
- **RRP_positive**: float, un RRP positivo promediado, ponderado por la demanda diaria correspondiente en AUD$ / MWh.
- **demand_neg_RRP**: float, demanda diaria total con RRP negativo en MWh.
- **RRP_negative**: flotante, un RRP negativo medio, ponderado por la demanda diaria correspondiente en AUD$ / MWh.
- **frac_at_neg_RRP**: flotante, fracción del día en que la demanda se negoció a RRP negativo.
- **min_temperature**: flotante, temperatura mínima durante el día en grados Celsius.
- **max_temperature**: flotador, temperatura máxima durante el día en grados Celsius.
- **exposición_solar**: flotante, energía solar diaria total en MJ/m².
- **precipitación**: float, precipitación diaria en mm.
- **día_escolar**: booleano, si los alumnos estaban en el colegio ese día.
- **día_festivo**: booleano, si el día era festivo nacional o estatal.

En el análisis se pretende comprobar que la técnica de suavizado exponencial, un algoritmo de series temporales, realiza una buena predicción de la demanda eléctrica. Se apuesta por esta técnica ya que es capaz de incorporar efectos como el nivel de la serie, la tendencia y la estacionalidad. Para poder llevar a cabo esto, el algoritmo posee tres grandes variaciones, el suavizado exponencial simple, para datos sin tendencia ni estacionalidad, el doble para datos con tendencia sin estacionalidad, y el triple, como sería en nuestro caso, para datos con ambos efectos. Este modelo suele funcionar mejor que el ARIMA en casos más microeconómicos como la predicción de la demanda.
