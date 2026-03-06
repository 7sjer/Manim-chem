# Manim-chem
%%manim -v WARNING Chmicalbond
from manim import *


class Chmicalbond(Scene):
  def construct(self):
      P = RegularPolygon(
      n=6, color=WHITE, fill_opacity=1, stroke_width = 10, stroke_color =      BLUE).scale(1.4)
    T = Text("Benzene ring", font_size=30, color=BLUE)
    D = Dot(color=BLUE)
    T.next_to(P,DOWN , buff = 1)
    self.play(Create(P),Create(D), run_time=2)
    self.play(P.animate.rotate(1/2))
    self.play(
        D.animate.shift(DOWN*3)
    )
    self.play (Transform(D,T))
    Vert= P.get_vertices()

    
  for i in [0,2,4]:
      L = Line(Vert[i],Vert[1+i],color = BLUE,stroke_width = 10).scale(0.8)
      L.shift((P.get_center()-L.get_center())*0.2)
      self.play(Create(L))
    self.wait(4)



