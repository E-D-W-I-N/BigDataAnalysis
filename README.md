# Лабораторная работа №6
# Измерение и анализ интернет-соединения, визуализация результатов

## Контрольные вопросы

1. Какие типы были у записей в `df_compact` до преобразования?
    
    | Column            | Type    |
    | ----------------- | ------- |
    | Ping (ms)         | object  |
    | Download (Mbit/s) | object  |
    | Upload (Mbit/s)   | float64 |
    | Date              | object  |
    | Time              | object  |
    
2. В какое время наблюдалась максимальная и минимальная скорость загрузки, выгрузки данных, задержки отправки эхо-запросов командой ping?

    | Parameter      | Min      | Max      |
    | -------------- | -------- | -------- |
    | Ping           | 15:26:20 | 17:30:06 |
    | Download speed | 14:57:55 | 17:02:49 |
    | Upload speed   | 17:31:47 | 18:02:15 |
    
3. Каким получился результат коррелиционного анализа?

    |                | Ping          | Download speed | Upload speed     |
    | -------------- | ------------- | -------------- | ---------------- |
    | Ping           | 1.000000      | -0.045626      | -0.463099        |
    | Download speed | -0.045626     | 1.000000       | 0.083690         |
    | Upload speed   | -0.463099     | 0.083690       | 1.000000         |
    
4. Каков точный формат задания подписей к осям графика, наименования графика, добавления легенды для выводимых на график величин?

    Форматы задания этих вещей наиболее подробно описываются в официальной документации:
    
    * Формат задания подписей к осям графика:
        * Ось X:

            `Axes.set_xlabel(self, xlabel, fontdict=None, labelpad=None, *, loc=None, **kwargs)`

            | Parameters            | Decsription    |
            | --------------------- | -------------- |
            | xlabel : str          | The label text |
            | labelpad : float      | Spacing in points from the axes bounding box including ticks and tick labels. If None, the previous value is left as is.|
            | loc : {'left', 'center', 'right'}| The label position. This is a high-level alternative for passing parameters x and horizontalalignment.|
            | **kwargsText properties| Text properties control the appearance of the label.|
        
        * Ось Y:

            `Axes.set_ylabel(self, ylabel, fontdict=None, labelpad=None, *, loc=None, **kwargs)`

            | Parameters            | Decsription    |
            | --------------------- | -------------- |
            | ylabel : str          | The label text |
            | labelpad : float      | Spacing in points from the axes bounding box including ticks and tick labels. If None, the previous value is left as is.|
            | loc : {'bottom', 'center', 'top'}| The label position. This is a high-level alternative for passing parameters y and horizontalalignment.|
            | **kwargsText properties| Text properties control the appearance of the label.|
        
    * Формат задания наименование графика:

        `Axes.set_title(self, label, fontdict=None, loc=None, pad=None, *, y=None, **kwargs)`
    
        | Parameters            | Decsription    |
        | --------------------- | -------------- |
        | label : str           | Text to use for the title |
        | fontdict : dict       | A dictionary controlling the appearance of the title text |
        | loc : {'center', 'left', 'right'}| Which title to set|
        | y : float             | Vertical Axes loation for the title (1.0 is the top). If None (the default), y is determined automatically to avoid decorators on the Axes.|
        | pad : float           | The offset of the title from the top of the Axes, in points.|
        | **kwargsText properties| Other keyword arguments are text properties, see Text for a list of valid text properties.|
    
     * Формат добавление легенды:

        `matplotlib.pyplot.legend(*args, **kwargs)`
     
     Аргументов там слишком много, сюда в таблицу не все не влезет. Подробно о кадом аргументе можно прочитать [тут](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.legend.html).
     
5. Какие ещё библиотеки применяются для визуализации данных Python, назовите и кратко опишите пять таких библиотек.

    * **Seaborn** — это библиотека для создания статистических графиков на Python. Она основывается на `matplotlib` и тесно взаимодействует со структурами данных pandas.
    * **Plotly** — это библиотека для создания интерактивных визуализаций и управления ими. В этой, написанной на `JavaScript` библиотеке, есть множество встроенных функций, что упрощает реализацию и визуализацию разных алгоритмов.
    * **Altair** - это декларативная библиотека статистической визуализации для Python, основанная на vega-lite. Altair можно считать промежуточным звеном между Seaborn и Plotly, поскольку она более настраиваемая, чем Seaborn, но не настолько интерактивна как Plotly.
    * **Bokeh** - это интерактивная библиотека для визуализации, предназначенная для презентации данных в браузерах.
    * **Folium** - позволяет легко визуализировать данные на интерактивной встраиваемой карте. В библиотеке есть несколько встроенных тайлсетов из OpenStreetMap, Mapbox и Stamen.
