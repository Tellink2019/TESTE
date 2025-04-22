import { motion } from "framer-motion";
import { Carousel } from "@/components/ui/carousel";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { FaWifi, FaCamera, FaBolt, FaBuilding, FaUserShield } from "react-icons/fa";

export default function Principal() {
  return (
    <div className="bg-white text-black">
      {/* Seção de Planos */}
      <section className="p-6">
        <h2 className="text-3xl font-bold mb-4 text-center">Nossos Planos</h2>
        <Carousel>
          {[300, 450, 100, 150, 600, 1000].map((velocidade) => {
            const plano = {
              100: { preco: "R$ 49,90", desc: "Wi-Fi 5 - Consulte taxa de instalação", icone: <FaWifi /> },
              150: { preco: "R$ 59,90", desc: "Wi-Fi 5 - 50% na 1ª parcela", icone: <FaWifi /> },
              300: { preco: "R$ 69,90", desc: "Wi-Fi 5 - 50% na 1ª parcela", icone: <FaWifi /> },
              450: { preco: "R$ 79,90", desc: "Wi-Fi 5 - 50% na 1ª parcela", icone: <FaWifi /> },
              600: { preco: "R$ 99,90", desc: "Wi-Fi 6 - 50% nas 4 primeiras parcelas", icone: <FaWifi /> },
              1000: { preco: "R$ 199,90", desc: "2 câmeras IA ou alarme incluso", icone: <FaCamera /> },
            }[velocidade];

            return (
              <Card key={velocidade} className="w-72 m-2">
                <CardContent className="flex flex-col items-center gap-2 p-4">
                  <motion.div whileHover={{ scale: 1.1 }} className="text-4xl">
                    {plano.icone}
                  </motion.div>
                  <h3 className="text-xl font-bold">{velocidade === 1000 ? "1 GIGA" : `${velocidade} MEGA`}</h3>
                  <p className="text-lg font-semibold text-red-600">{plano.preco}</p>
                  <p className="text-center text-sm">{plano.desc}</p>
                  <Button className="mt-2 w-full">Assinar</Button>
                </CardContent>
              </Card>
            );
          })}
        </Carousel>
      </section>

      {/* Seção de Soluções Empresariais */}
      <section className="bg-gray-100 p-6">
        <h2 className="text-2xl font-bold mb-4 text-center">Soluções Empresariais</h2>
        <div className="grid md:grid-cols-3 gap-4">
          <Card>
            <CardContent className="p-4">
              <FaBuilding className="text-3xl mb-2" />
              <h3 className="font-bold">Internet Dedicada</h3>
              <p>Alta performance com estabilidade garantida para empresas.</p>
            </CardContent>
          </Card>
          <Card>
            <CardContent className="p-4">
              <FaCamera className="text-3xl mb-2" />
              <h3 className="font-bold">Monitoramento Inteligente</h3>
              <p>Câmeras com IA, alarmes e notificações em tempo real.</p>
            </CardContent>
          </Card>
          <Card>
            <CardContent className="p-4">
              <FaUserShield className="text-3xl mb-2" />
              <h3 className="font-bold">Consultoria Empresarial</h3>
              <p>Projetos personalizados de conectividade e segurança.</p>
            </CardContent>
          </Card>
        </div>
      </section>

      {/* Feedbacks */}
      <section className="p-6">
        <h2 className="text-2xl font-bold mb-4 text-center">O que dizem nossos clientes</h2>
        <div className="grid md:grid-cols-2 gap-4">
          {[1, 2, 3, 4].map((n) => (
            <Card key={n} className="shadow">
              <CardContent className="p-4">
                <p className="italic">"Atendimento excelente, internet super rápida e confiável!"</p>
                <p className="text-right text-sm mt-2">– Cliente {n}</p>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>

      {/* Rodapé */}
      <footer className="bg-black text-white p-6 text-sm">
        <div className="flex flex-col md:flex-row justify-between items-center gap-4">
          <div>
            <p><strong>CNPJ:</strong> 38.346.388/0001-50</p>
            <p><strong>WhatsApp:</strong> (83) 98128-6950</p>
            <p><strong>Email:</strong> tell.linktelecom@gmail.com</p>
            <p><strong>Instagram:</strong> @tellink_telecom</p>
            <p><strong>Endereço:</strong> Rua Pedro Álvares Cabral, 529, Loja 102</p>
          </div>
          <p className="text-center md:text-right">© {new Date().getFullYear()} Tellink Telecom. Todos os direitos reservados.</p>
        </div>
      </footer>
    </div>
  );
}
