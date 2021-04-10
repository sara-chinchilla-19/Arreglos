# Arreglos
using Arreglo_Nota.Properties;
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace listadopromedio
{
    public partial class Form1 : Form
    {

        private string[] ArregloNotas;


        public Form1()
        {
            InitializeComponent();
        }

        private void buttonArreglo_Click(object sender, EventArgs e)
        {
            int[] arreglo = new int[5];
            arreglo[0] = 100;
            arreglo[1] = 8;
            arreglo[2] = 16;
            arreglo[3] = 700;
            arreglo[4] = 5;

            ClsArreglos ObjetoArreglo = new ClsArreglos(arreglo);
            int[] resultado = ObjetoArreglo.MetodoBurbuja();


            foreach (int r in resultado)
            {
                listBoxResultado.Items.Add(r);

            }
        }

        private void CargarArchivo_Click(object sender, EventArgs e)
        {
            ClsArchivo ar = new ClsArchivo();
            OpenFileDialog ofd = new OpenFileDialog();

            ofd.Title = "Porfavor, seleccionar tu archivo plano";
            ofd.InitialDirectory = @"C:\Users\Sarita Chinchilla\OneDrive\Escritorio\5to.Semestre\Progra 1\Nueva carpeta\Archivo Plano.csv";
            if (ofd.ShowDialog() == DialogResult.OK)
            {
                var archivo = ofd.FileName;
                string resultado = ar.LeerTodoArchivo(archivo);
                ArregloNotas = ar.LeerArchivo(archivo);
                textBoxResultado.Text = resultado;
            }


        }

        private void listBox1_SelectedIndexChanged(object sender, EventArgs e)
        {

        }
    }
}
    }
}
