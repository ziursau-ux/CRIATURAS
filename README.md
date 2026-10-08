"# CRIATURAS" 
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Drawing;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace primera
{
    internal class Sirena : Criatura
    {

        int voz;

        public Sirena(string nombre, int voz, int energia, int velocidad, int salud, int felicidad, string habilidad, Color color)
            : base(energia, velocidad, salud, felicidad, nombre, habilidad, color)
        {
            this.Voz = voz;
        }

        public int Voz { get => voz; set => voz = value; }

        public override string Acariciar()
        {
            Felicidad += 20;
            Voz += 5;
            return Nombre + " canto de alegria. Felicidad: + 20, Voz: + 5";
        }

        public override string Entrenar()
        {
            Velocidad += 15;
            Energia -= 20;
            return Nombre + " canto en el mar. Velocidad: + 15, Energia: - 20 ";
        }

        public override string UsarHabilidad(Form1 f)
        {
            if (voz < 10)
            {
                MessageBox.Show(Nombre + " no tiene suficiente voz para usar su habilidad.");
                return Nombre + " intento cantar sin voz.";
            }
            Voz -= 10;
            Energia -= 10;
            Felicidad += voz / 5;
            f.BackColor = Color;
            return Nombre + " uso su canto. Voz: - 10, Energia: - 10";
        }


    }
}

