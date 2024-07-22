 Importar las bibliotecas necesarias
import streamlit as st
import pandas as pd
import plotly.express as px

def main():
    # Ruta del archivo
    archivo = 'D:\\descarga\\vehicles_us.csv'

    # Leer el archivo CSV
    df = pd.read_csv(archivo)

    # Crear el encabezado de la aplicación web
    st.header('Análisis exploratorio de datos')

    # Crear un botón para generar el histograma
    if st.button('Generar histograma'):
        # Crear el histograma con plotly express
        fig = px.histogram(df, x="odometer")
        
        # Mostrar el histograma en la aplicación web
        st.plotly_chart(fig)

if __name__ == "__main__":
    main()